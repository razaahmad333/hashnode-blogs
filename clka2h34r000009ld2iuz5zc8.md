---
title: "Creating an Immersive Experience with a Free RestAPI in a Static Website"
datePublished: Wed Jul 19 2023 18:38:30 GMT+0000 (Coordinated Universal Time)
cuid: clka2h34r000009ld2iuz5zc8
slug: creating-an-immersive-experience-with-a-free-restapi-in-a-static-website
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689791230617/6937cacd-2fee-4a6a-a874-305bfb6ec1e5.png
tags: jquery, web-development, html5, rest-api

---

Hey there!

I hope you're doing well!

Today, I found a RestAPI while looking at an old project. It was just sitting there in a javascript file, not being used. I'm not sure why I left it there, but when I checked out this API, I got an idea. I thought it would be cool to create a website with a nice design and colours using this API.

The API's URL is [https://www.boredapi.com/api/activity](https://www.boredapi.com/api/activity)

Feel free to check it out and use it to make something awesome!

The response of the above API ( every time you call this API it gives you are random response/activity )

```json
{
    "activity": "Write a note of appreciation to someone",
    "type": "social",
    "participants": 1,
    "price": 0,
    "link": "",
    "key": "1770521",
    "accessibility": 0
}
```

One interesting idea that popped into my head was to set the theme of each card based on the type of activity. To achieve this, I consulted ChatGPT, which provided me with an object containing keys representing the activity types and corresponding color codes as values.

```javascript
const activityThemes = {
    education: "#3498db",
    recreational: "#2ecc71",
    social: "#e67e22",
    diy: "#d35400",
    charity: "#9b59b6",
    cooking: "#f1c40f",
    relaxation: "#3498db",
    music: "#e74c3c",
    busywork: "#95a5a6"
}
```

Now, I was all set and ready to proceed...

Recently, I've become quite fond of jQuery. I mean, why bother with vanilla JavaScript and writing long lines like `document.querySelector` when you can simply use `$("#findme")`.

This website is written using CSS only, with no styling framework.

As for the user interface, it followed a minimalistic design with three main pages: the homepage, the saved activities page, and the settings page.

The live website: [https://cosmic-sherbet-a5c655.netlify.app/](https://cosmic-sherbet-a5c655.netlify.app/) ( it is only mobile responsive )

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689789247802/f2a2e7b9-d12a-4e4f-9b18-f62946281f46.png align="center")

To simplify the process, I store all the configuration data in the local storage, eliminating the need for user registration and login.

Whenever a new button is clicked, I have created a function called `fetchActivity` to retrieve a new activity. Here's the function:

```javascript
function fetchActivity() {
    onLoading()
    const accessibility = Number(localStorage.getItem("accessibility") || "-1")
    const type = localStorage.getItem("type") || "all"
    const participants = localStorage.getItem("participants") || "-1"
    const queries = {
        ...(accessibility !== -1 && { accessibility }),
        ...(type !== "all" && { type }),
        ...(participants !== "-1" && { participants })
    }

    fetch(`https://www.boredapi.com/api/activity?${$.param(queries)}`)
        .then((res) => res.json())
        .then((data) => {
            if (data.error) {
                alert(data.error + "\n\n" + "Try changing your settings")
                return
            }
            populateCard(data)
            currentActivity = data
            onLoadingComplete()
        })
}
```

The `onLoading` function is responsible for reducing the opacity of the card, indicating that data is being loaded, and it also disables the button.

On the other hand, the `onLoadingComplete` function does the opposite - it restores the card's opacity and enables the button.

The `populateCard` function is in charge of filling the card with activity data.

```javascript
function populateCard(activity) {
    $("#activity-text #activity-name").text(activity.activity)
    $("#activity-text #activity-type").text(activity.type)
    $("#activity-text #participants").text(activity.participants)

    $("#activity-text #activity-type").css("color", activityThemes[activity.type])
    $("#activity-buttons #save-button").css("background-color", activityThemes[activity.type])
    $("#activity-buttons #new-button").css("background-color", activityThemes[activity.type])
    if (activity.link) {
        $("#activity-text #activity-link").attr("href", activity.link)
        $("#activity-text #activity-link").text(activity.link)
    } else {
        const link = "https://www.google.com/search?q=" + activity.activity.replace(" ", "+") + "&tbm=isch"
        $("#activity-text #activity-link").attr("href", link)
        $("#activity-text #activity-link").text("how about you google it?")
    }

    const savedActivities = JSON.parse(localStorage.getItem("savedActivities") || "[]")
    if (savedActivities.includes(activity.key)) {
        $("#activity-buttons #save-button").attr("disabled", true)
        $("#activity-buttons #save-button").text("Saved")
    } else {
        $("#activity-buttons #save-button").attr("disabled", false)
        $("#activity-buttons #save-button").text("Save")
    }
}
```

To save the activity, I have created another function where I utilize the `currentActivity` variable, which is assigned a value when a new activity is fetched.

```javascript

$("#activity-buttons #save-button").click(() => {
    onLoading()
    const savedActivities = JSON.parse(localStorage.getItem("savedActivities") || "[]")
    savedActivities.push(currentActivity.key)
    localStorage.setItem("savedActivities", JSON.stringify(savedActivities))
    onLoadingComplete()
    populateCard(currentActivity)
})
```

Now, let's move on to the saved activities page, which happens to be my favourite part. Here, since I didn't have a way to send multiple keys to retrieve the list of saved activities, I made use of `Promise.all`.

First, I retrieve the saved activities from the local storage and parse them into an array:

```javascript
const savedActivities = JSON.parse(localStorage.getItem("savedActivities") || "[]");
```

Next, I define a function called `fetchAllActivities` that performs the following steps:

1. It creates an array of promises by mapping over the `savedActivities` array and fetching the data using the corresponding activity key:
    

```javascript
const promises = savedActivities.map(activity => {
    return fetch(`https://www.boredapi.com/api/activity?key=${activity}`);
});
```

1. It uses `Promise.all` to wait for all the promises to resolve, and then processes the responses:
    

```javascript
Promise.all(promises)
    .then(responses => {
        const jsonPromises = responses.map(response => response.json());
        return Promise.all(jsonPromises);
    })
    .then(activities => {
        console.log(activities);
        populateActivities(activities);
    });
```

This code snippet retrieves the activity data for each saved activity key, converts the responses to JSON, and finally calls the `populateActivities` function to display the activities on the page.

```javascript
const savedActivities = JSON.parse(localStorage.getItem("savedActivities") || "[]")

const fetchAllActivities = () => {
    const promises = savedActivities.map(activity => {
        return fetch(`https://www.boredapi.com/api/activity?key=${activity}`)
    })

    Promise.all(promises)
        .then(responses => {
            const jsonPromises = responses.map(response => response.json())
            return Promise.all(jsonPromises)
        })
        .then(activities => {
            console.log(activities)
            populateActivites(activities)
        })
}
```

Now, let's move on to the third page, the settings page.

My main objective for this page was to create a playful and user-friendly interface, without adding unnecessary complexity. I believe I was able to achieve that to some extent.

On the settings page, I included a "Restore Defaults" button which removes any custom configurations and reverts to the default settings. Additionally, I provided default values for all filters and settings.

During the process of fetching data, if a filter or setting is set to its default value, I don't send a query for that particular filter, allowing for a smoother and more streamlined experience.

### Conclusion

From a basic RestAPI to a cool website, I embarked on a journey of exploration and innovation. I wanted to create a website that would give users an awesome experience. So, I matched different activities with cool visual styles, simplified the code using jQuery, and made the settings easy to understand. The result was a website that captivated users and allowed them to discover and enjoy exciting activities. Along the way, I learned the importance of being resourceful, open to unexpected discoveries, and focusing on what users really want.

Thank you for reading so far.

Here is the source code of the website : [https://github.com/razaahmad333/Getting\_bored](https://github.com/razaahmad333/Getting_bored)