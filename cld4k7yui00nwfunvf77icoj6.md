# What, why and How CSS 🤔

CSS stands for Cascading Style Sheet. It is used to style the web page.

CSS is a very powerful tool that can transform not so good looking HTML webpage into a good-looking webpage.

For example, it can transform

**This ugly-looking webpage:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674113700404/7aad5727-bd5e-4822-9484-767ee275eded.png )

**Into this:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674113780117/2baa0c32-e794-4533-9eb5-6560c3fb0b07.png )

---

### How to CSS? 🦜

Create a folder on your desktop `my-website` .

Inside that folder create two files

* `index.html` to create a webpage
    
* and `style.css` ( you can name your stylesheet whatever you want, but it should end with `.css` )
    

Inside `index.html` write the code:

```xml
<!DOCTYPE html>
<html lang="en">

    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, 
              initial-scale=1.0">
        <title>CSS3 | What why and How CSS</title>
    </head>

    <body>
        <h1>
            CSS is a language that describes the style of an HTML document.
        </h1>
    </body>

</html>
```

and in `style.css` write:

```css
h1 {
  color: red;
}
```

For now, you will see no effect of style.css on the webpage, because they are not connected yet.

You will get to see the webpage ( if you open `index.html` in a browser ) like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674191992258/00247e95-e89d-4afd-ab9b-d72abd19dec7.png )

---

### So, How to connect the stylesheet (`style.css`) to an HTML file? 🔗

It's very simple. Just put the relative path of that stylesheet in a `<link>` tag into `<head> </head>` of the HTML file.

The code:

```markdown
<link rel="stylesheet" href="./style.css">
```

Now, after putting `link` your `index.html` file will look like this:

```xml
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, 
                initial-scale=1.0">
        <link rel="stylesheet" href="./style.css">
        <title>CSS3 | What why and How CSS</title>
    </head>
    <body>
        <h1>
            CSS is a language that describes the style of an HTML document.
        </h1>
    </body>
</html>
```

And your webpage will look like this:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674192385100/024b6341-ddcf-4196-8800-7874b7eb8a20.png )

![Wander Over Yonder Congrats GIF - Wander Over Yonder Congrats Congratulations GIFs](https://media.tenor.com/h9zIaweIRxwAAAAM/wander-over-yonder-congrats.gif )

Congratulations 🎉, you just wrote a stylesheet and connected it to an HTML file.

---

### You can also write CSS within the HTML file 🎗️

The CSS styling can also be achieved in these two ways:

1. Write styling inside `<style> </style>` tag into `<head> </head>` of HTML file ( Internal CSS )
    
    ```xml
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, 
                  initial-scale=1.0">
            <title>CSS3 | What why and How CSS</title>
            <style>
                h2 {
                    color: green;
                }
            </style>
        </head>
        <body>
           <h2>
                This is styled by Internal CSS
          </h2>
        </body>
    </html>
    ```
    
    > ⚡If the size of stylesheet file is huge, so it becomes hard to work with this structure.
    
2. Write the required styling into that particular tag:
    
    ```xml
    <h3 style="color: blue;">
        This is inline CSS.
    </h3>
    ```
    
    > ⚡This structure of styling do not provides scaling. If you have 10 `h3` tags and you want to make each of them blue, then you will have to style each tag manually.
    

---

### Let's understand the CSS code snippet we wrote above: 🧑‍🏫

```css
h1 {
  color: red;
}
```

It says, "select every `h1` tag in that HTML file and set its text color to red".

CSS is so simple, actually entire web development is simple. Computers are simple as they only understand "1" and "0".

It becomes hard when complexity arises.

---

### How much power CSS holds ⚡

Someone on the internet has created the Mona Lisa painting with pure CSS.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674195722926/62eae3ae-57b9-48c2-aae9-f7df1d7e1dbd.png )

🔗 [Check out the CSS code for Mona Lisa Painting](https://css-art.com/mona-lisa/source.html)

Check out [css-art](https://css-art.com/) website, to see more CSS arts other than designing webpages.

Ultimately all the designing and styling of CSS is done on a webpage. Each CSS needs an HTML file.

---

### Source Codes 💠

* [Click here](https://github.com/WebD-Essentials/CSS3/archive/refs/heads/what-why-and-how-css.zip) to download the source code of this blog.
    
* [Here](https://github.com/WebD-Essentials/CSS3/tree/what-why-and-how-css) is the source code of this blog on GitHub.
    
* [Live](https://webd-essentials.github.io/CSS3/what-why-and-how-css/) Preview of the codes in this blog.
    

In the next blog, We will be learning about the ways you can select tags/elements from HTML files to style them.