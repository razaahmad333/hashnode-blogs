# Styling texts with CSS 👕

A piece of text has a lot of properties that can be tweaked to change its appearance on a webpage.

```xml
<p id="para1">
    a really nice quote
</p>
<p id="para2">
    a really nice quote
</p>
<p id="para3">
    a really nice quote
</p>
<p id="para4">
    a really nice quote
</p>
```

The list of properties of texts are:

### Color

determines the color of a text

```css
#para1 {
  color: red;
}

#para2 {
  color: rgb(23, 45, 67);
}

#para3 {
  color: #ffc40b;
}

#para4 {
  color: hsl(120, 100%, 50%);
}
```

There are a few ways to pass the value of color itself:

* name of the color, ex: **red**, **blue**, **green**
    
* RGB value, ex: **rgb(12, 22, 44)** | RGBA value, ex: **rgba(212, 82, 144, 0.8)**
    
* Hex code, ex: #23adfe
    
* HSL value, ex: **hsl(9, 100%, 64%)** | HSLA value ex: **hsla(9, 100%, 64%, 0.5)**
    

🔗 [Here are the names of almost all the colors in CSS](https://www.w3.org/wiki/CSS/Properties/color/keywords)  
🔗 [Hex color codes](https://htmlcolorcodes.com/)

🔗 [Color picker](https://fffuel.co/cccolor/)

---

### Font-size

determines the size of the text

```css
#para1 {
  font-size: 24px;
}

#para2 {
  font-size: 1.4em;
}

#para3 {
  font-size: 1.3rem;
}

#para4 {
  font-size: 0.5in;
}
```

There are a lot of units for font-size values, such as `px` `pt` `em` `rem` `in` `cm` .

🔗 [Here you can read more about them.](https://www.w3.org/Style/Examples/007/units.en.html)

---

### Font-family

determines the appearance of text.

```css
#para1 {
  font-family: Arial, Helvetica, sans-serif;
}
```

CSS has five generic font-families `serif` `sans-serif` `monospace` `cursive` `fantasy` .

There are a lot of other fonts available but they may not be compatible across all

browsers and devices. Thats why while the passing value in `font-family` property

we start with a font that we want and end with any one generic font for fallback.

[Google fonts](https://fonts.google.com/) have more than 1400 fonts that you can use.

How to use google fonts?

* Go to [https://fonts.google.com/](https://fonts.google.com/) official website
    
* Choose any font
    
* Copy the `<link>` code and paste it into HTML file
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674747686754/1b4336e6-9ece-45fc-9bfe-fbe51980396c.png)
    
* And copy the CSS code and paste it wherever you want to apply that font.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674747785129/e9f6a70e-530a-412c-b015-50ad95da61ff.png)
    

---

### Text decoration

Adds decoration to text, basically a line.

```css
p {
  text-decoration: underline;
}
```

The possible values are `none` `underline` `line-through` `overline` `underline overline` .

---

### Letter Spacing

As the name suggests, it sets the space between letters.

```css
p {
  letter-spacing: 0.5px;
}
```

---

### Line Height

Sets the distance between lines.

```css
p {
  line-height: 20px;
}
```

---

### Text Transform

Controls the capitalization of text.

```css
p {
  text-transform: uppercase;
}
```

The possible values are `uppercase` `lowercase` `capitalize`.

---

### Text Align

Sets the alignment of text

```css
p {
  text-align: center;
}
```

The possible values are `left` `right` `center` `justify`.

---

### Text Shadow

Gives shadow to the text.

```css
p {
  text-shadow: 2px 2px red;
}
```

In the value, first `2px` determines horizontal shadow, second `2px` determines vertical shadow and the last value determines the color of the shadow.

[Read more about text-shadow at W3Schools](https://www.w3schools.com/css/css_text_shadow.asp).

---

### Exercises 🏌️

[Here](https://www.w3schools.com/css/exercise.asp?filename=exercise_text1) are some **easy** and **worth practicing** exercises on W3Schools.

---

### Source Codes 💠

* [**Click here**](https://github.com/WebD-Essentials/CSS3/archive/refs/heads/styling-texts-with-css.zip) to download the source code of this blog.
    
* [**Here**](https://github.com/WebD-Essentials/CSS3/tree/styling-texts-with-css) is the source code of this blog on GitHub.
    
* [**Live**](https://webd-essentials.github.io/CSS3/styling-texts-with-css/) Preview of the codes in this blog.