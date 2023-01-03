# Images, audio, video and iframe in HTML 🎬

Adding images, icons, audio and videos, and other visuals gives the website a nice look and also serves various purposes.

Let's see their codes and concepts.

> ⚡ [Download](https://github.com/WebD-Essentials/HTML5/archive/refs/heads/images-audio-and-video-etc.zip) and extract the source code of this blog. Edit these codes in your computer and try different possible combinations.

### Images 🖼️

I have created a file `index.html` and the code to display an image is:

```xml
<img src="./images/bags.jpg" alt="a bag">

<img src="./pencil.jpg" alt="a pencil" width="100" height="100">

<img src="https://cdn.pixabay.com/photo/2018/04/26/16/39/beach-3352363__340.jpg" alt="a beach">
```

[Checkout live preview of the above code](https://webd-essentials.github.io/HTML5/images-audio-and-video-etc#images)

**The explanation for the above code:**

* `<img >` is an inline-level tag.
    
* Professionals say always use `alt` attribute to explain the image. Because sometimes images take time to download on the webpage and in that meantime, the text passed in `alt` attribute is visible to the user or reader.
    

> ⚡It is also possible that the image file is corrupted or the path passed to `src` is wrong. In those situations `alt` attribute is very useful to explain the image.

* `src` attribute is used to give the path of the image source to `<img>` tag.
    

**In the** `src` **attribute, I have passed paths like this**

* `./images/bags.jpg`
    
* `./pencil.jpg`
    
* `https://cdn.pixabay.com/photo/2018/04/26/16/39/beach-3352363__340.jpg`
    

**My directory structure is:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672720730300/54ffeaa5-53df-43d3-885d-cd28f1c954fb.png)

### What are these paths?

Here `./images/bags.jpg` is the relative path of `bags.jpg` image from `index.html` file and `bags.jpg` is in `images` folder.

* `.` says, you are in the current directory of the file in which the path is written. Here it is `index.html` and now you can access `images` folder, `pencil.jpg` image, etc.
    
* using `/` , enter a folder name to go to or a file name to use. Here `./images` means you entered into `images` folder.
    
* Now further adding `/bags.jpg` to `./images` completes the relative path of `bag.jpg` image from `index.html`. And `./images/bags.jpg` says you are pointing to the bag image source.
    

Now, it is easy to understand the path `./pencil.jpg` , as `pencil.jpg` is in the same directory of `index.html` . I have used `.` to go into the current directory and `/pencil.jpg` to point the `pencil.jpg` image.

**The third path** `https://cdn.pixabay.com/photo/2018/04/26/16/39/beach-3352363__340.jpg` **is the external URL for an image source. This image is not present in my local machine's directory.**

[Read More about &lt;img&gt; - Official Docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)

---

### Audios 🎶

```xml
<audio src="./peaceful_music.mp3" controls> </audio>

<audio src="https://www2.cs.uic.edu/~i101/SoundFiles/StarWars60.wav" controls="true" autoplay muted> </audio>
```

[Check out the live preview of the above code](https://webd-essentials.github.io/HTML5/images-audio-and-video-etc#audios).

The above code adds an element to the webpage with controls.

**Something like this:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672641006586/1a16213a-8f47-4b81-83d6-86a7f1029ee4.png)

In `src` ( source ) attribute takes the path of the source of audio files. I have two audio files, first one exists on my computer and the second is coming from an external source using a URL.

Here, passing `controls` attribute without any value means `controls="true"` .

Controls are play, progress slider, volume, and download button.

You can check other attributes like `muted` , `autoplay` etc.

[Read more about the audio tag - Official Docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)

> ⚡If you want to add music effects ( means that play when some button is clicked or something ), use Javascript for that.

---

### Videos 🎥

If you have a video file available on your local machine or from an external source. Use `<video> </video>` tag for that.

```xml
<h4>From external source</h5>
<video src="https://storage.googleapis.com/gtv-videos-bucket/sample/ElephantsDream.mp4" width="600" controls loop>
</video>

<h4>From local source</h4>
<video src="./videos/mov_bbb.mp4" width="500" controls>
</video>
```

[Check out the live preview of the above code.](https://webd-essentials.github.io/HTML5/images-audio-and-video-etc#videos)

Everything here is self-explanatory. `src` attribute is used to give path to video tags and other attributes such as `width`, `controls`, `loop` determines its other required properties.

[Read more about the video tag - Official Docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

---

### iframes 🎞️

`<iframe> </iframe>` are used to embed external web pages in your website as a frame.

In most cases, you don't need to write the code for iframe if you want to embed a youtube video or a google maps location on your website. Just go to the website and copy the iframe code.

On Youtube, click on `Share` button, then click on `Embed` button, now you will see the code of the iframe for that video. Copy the code from there and paste it into your HTML file.

Most of the websites which provide iframe have the iframe codes in their `Share` button.

```xml
<h4>Spotify iframe</h4>
<iframe style="border-radius:12px"
    src="https://open.spotify.com/embed/track/3VM35337X7Ro1tesUHnZ95?utm_source=generator" width="100%"
    height="352" frameBorder="0" allowfullscreen=""
    allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
    loading="lazy"></iframe>

<h4>Youtube iframe</h4>
<iframe width="560" height="315" src="https://www.youtube.com/embed/MhTDp5FwfmM" frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen></iframe>

<h4>Google iframe</h4>
<iframe
    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3169.8198184838316!2d-122.15238048475987!3d37.39409317983052!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x808fb075776f1c3b%3A0xccc17e4da6b38370!2sTesla%20HQ!5e0!3m2!1sen!2sin!4v1672715268459!5m2!1sen!2sin"
    width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"
    referrerpolicy="no-referrer-when-downgrade"></iframe>
```

[Check out the live preview of the above code.](https://webd-essentials.github.io/HTML5/images-audio-and-video-etc#iframes)

[Read more about iframes - Official Docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe).

---

### Icons 🥼

There are a lot of possible ways you can put icons on your page.

There are websites that provide icons to use for **FREE**. Here I'm using [Font-Awesome](https://fontawesome.com/icons) icons.

There are two steps required

* First step, copy and paste their `cdn url` inside `<head> </head>` tag of your HTML file.
    

```xml
<head>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
</head>
```

* Second step, use the icon
    

```xml
<i class="fa fa-cloud"></i>
<i class="fa fa-heart"></i>
<i class="fa fa-car"></i>
<i class="fa fa-file"></i>
<i class="fa fa-bars"></i>
```

Check their websites to use other icons available.

[For more information, and other possible ways to display icons, check w3schools](https://www.w3schools.com/icons/).

---

### Exercises 🏌️

Here are some **easy** and **worth** practicing exercises on W3Schools.

* [Images](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_images1)
    
* [iframes](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_iframe1)
    

---

### **Source Codes 💠**

[**Click here**](https://github.com/WebD-Essentials/HTML5/archive/refs/heads/images-audio-and-video-etc.zip) to download the source code of this blog.

[**Here is**](https://github.com/WebD-Essentials/HTML5/tree/images-audio-and-video-etc) the source code of this blog on GitHub.

[**Live Preview**](https://webd-essentials.github.io/HTML5/images-audio-and-video-etc/) of the codes in this blog.

In the next blog, I will be writing about Lists in HTML.