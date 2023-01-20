# Links and Navigation in HTML  🤝

You must have seen links, mostly blue color underlined texts starting with `https:` and ending with `.com` or `.in` etc. somewhere on your mobiles and web browsers. They usually take you to another screen or website and can also navigate within the page.

**A typical example of links could be search results on Google's webpage:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673001785160/bdf00a5b-58d0-4ef3-a0bf-8efdcdafc036.png )

### How to put a link on your webpage? 🤔

You can use an anchor tag for that `<a> </a>` .

**The code:**

```xml
<a href="https://google.com"> click me to go on google home page </a>
<br>
<a href="https://w3schools.com" target="_blank"> Click me to go on W3Schools home page </a>
```

[Check out the live preview of the above code](https://webd-essentials.github.io/HTML5/links-and-navigation#intro).

**The output of the above code:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673002494655/6d00d72b-3108-4fd4-ae12-d931cb9fa904.png )

**The breakdown of the code:**

* `<a> </a>` anchor tag is an inline-level tag, that's why I have used `<br>` tag to display them in separate lines.
    
* `href` attribute takes the address ( say link or URL ) of that other website.
    
* `target="_blank"` attribute opens that link in a new tab.
    

### Create more pages for your website and link them with `<a> </a>` tag 🖇️

Create four HTML files in your website's folder. (You can create HTML files with any name you want ). Each HTML file is a separate page of a website.

* `index.html` , this would be the homepage of your website
    
* `stories.html` , a page to write stories
    
* `about.html` , another page to write about yourself
    
* `projects.html` , a page to enlist all your projects.
    

**How I will connect these pages?**

I will use an anchor tag on each page and will give relative paths of other pages to `href` attribute, like `href="./projects.html` , `href="./stories.html"` etc.

For example: If I have two pages `index.html` and `stories.html` and I want to connect them.

**A visual representation:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673074669685/a2195695-b72e-45d9-9887-c65e497caa3a.png )

So in `index.html` , I will use an anchor tag and pass the path of `stories` page as `./stories.html` , because both the files are in the same directory.

```xml
<a href="./stories.html"> Go to Home Page </a>
```

and in `stories.html` , I would pass the path of `index` page as `./index.html` .

```xml
<a href="./index.html"> Go to Home Page </a>
```

**Let's say I have another file** `bikes.html` **in** `vehicles` **folder inside my website's folder.**

and I want to connect the `bikes` page to `index` page.

I would write the path in `index.html` as:

```xml
<a href="./vehicles/bikes.html"> Go to bikes pagees </a>
```

and in `vehicles/bikes.html` I would write the path of `index` page as

```xml
<a href="../index.html"> Go to homepage </a>
```

**My directory structure looks like this. The folder for my website is** `links-and-navigation` .

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673074198755/36cb9f6a-9598-4dc4-83b9-e30c4091d3d1.png )

### An example to summarize the above concept 🍭

**Here are the codes**

* `stories.html`
    
    ```xml
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title> Stories | Links and Navigation | HTML5</title>
        </head>
        <body>
            <h3>Stories Page</h3>
            <a href="./index.html"> Go to Home Page </a>
    
            <h4>Harry Potter</h4>
            <h4>Lord of the Rings</h4>
            <h4>Game of Thrones</h4>
        </body>
    </html>
    ```
    
    **The preview:**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673064465444/8dca698c-0d53-4da5-839c-109d3e7bbd62.png )
    
* `projects.html`
    
    ```xml
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title> Projects | Links and Navigation | HTML5</title>
        </head>
        <body>
            <h3> Future-Projects Page</h3>
            <a href="./index.html"> Go to Home Page </a>
    
            <h4>Project 1</h4>
            <h4>Project 2</h4>
        </body>
    </html>
    ```
    
    **The preview:**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673064556393/3380ddac-6c9a-4e69-8bae-c7d8126aa4d9.png )
    
* `about.html`
    
    ```xml
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title> About | Links and Navigation | HTML5</title>
        </head>
        <body>
            <h3>About Page</h3>
            <a href="./index.html"> Go to Home Page </a>
    
            <h4>My name is John Doe</h4>
            <p>
                Currently, I'm learning HTML5.
                I have also created a
                <a href="./stories.html">stories page,</a> and
                <a href="./projects.html"> a projects page </a>
            </p>
        </body>
    </html>
    ```
    
    **The preview:**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673064622014/7f3e41ae-0013-4b3d-94d9-92ff10933a1b.png )
    
* finally in `index.html` ,
    
    ```xml
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Links and Navigation | HTML5</title>
        </head>
        <body>
            <h1>Links and Navigation</h1>
    
            <hr>
            <h2>This is the homepage or landing of this website</h2>
            <hr>
    
            <h3 id="intro"> Introduction </h3>
            <a href="https://google.com"> click me to go google homepage </a>
            <br>
            <a href="https://w3schools.com" target="_blank"> Click me to go on W3Schools home page </a>
    
            <h3 id="internal-links"> Other pages of this website </h3>
            <br>
            <a href="./stories.html">
                Go to Stories Page
            </a>
            <br>
            <a href="./about.html">
                Go to About Page
            </a>
            <br>
            <a href="./projects.html">
                Go to Projects Page
            </a>
        </body>
    </html>
    ```
    
    **The preview:**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673064734733/498ff69c-f727-4c2e-914d-9fccb1a4c9ad.png )
    
    [<mark>Click here for the live preview of the above code</mark>](https://webd-essentials.github.io/HTML5/links-and-navigation)
    

### What is the navigation within the page?

There are links on a page when clicked scroll the page and takes you to the desired location within that page.

[See the example page here, click on the links of vegetable names and notice the scrolling effect](https://webd-essentials.github.io/HTML5/links-and-navigation/vegetables.html)

💠 [Here is the source code of the above page](https://github.com/WebD-Essentials/HTML5/tree/links-and-navigation/vegetables.html)

**Now, how you can code this in your webpage:**

There are two steps to it

* Give an `id` to the targeted content, which is somewhere on your webpage
    
    ```xml
    <div id="mango">
    Mango is the king of fruits
    </div>
    ```
    
* add a link, wherever you want ( within the same page ) and pass that id with `#` prefix.
    
    ```xml
    <a href="#mango"> take me to the mango content </a>
    ```
    

> ⚡`id` attribute should be unique within a page.
> 
> Two tags or html elements can't have same id.

---

### Exercises 🏌️

[Here](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_links1) are some **easy,** and **worth** practicing exercises on W3Schools.

---

### Source Codes 💠

* [Download](https://github.com/WebD-Essentials/HTML5/archive/refs/heads/links-and-navigation.zip) the source code of this blog.
    
* [Check](https://github.com/WebD-Essentials/HTML5/tree/links-and-navigation) the source code of this blog on GitHub.
    
* [Live Preview](https://webd-essentials.github.io/HTML5/links-and-navigation) of the codes of this blog.
    

In the next blog, I will be writing about [Forms and Input Elements in HTML](https://webdessentials.hashnode.dev/forms-and-input-elements-in-html).