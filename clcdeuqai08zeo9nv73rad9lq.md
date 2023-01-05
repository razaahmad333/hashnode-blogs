# Texts, headings and paragraphs in HTML 📜

You can display texts on your webpage in various formats using HTML, such as:

* Headings
    
* Paragraphs
    
* bold and italic texts, etc
    

> ⚡ Try copy-pasting the codes of this blog on [W3Schools Tryit Playground,](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_basic) Try different combinations, and see output instantly.

### Headings 🦒

There is a series of heading tags ( h1 to h6 ) to show headings in different sizes.

```xml

<h1> Heading with h1</h1>
<h2> Second Heading with h2</h2>
<h3> Third Heading with h3</h3>
<h4> Fourth Heading with h4</h4>
<h5> Fifth Heading with h5</h5>
<h6> Sixth Heading with h6</h6>
```

**The Output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671726508720/0f4ea498-efbc-4121-ba72-45689d54d45d.png)

You can also change the boldness and hugeness of these headings using CSS.

> ⚡ You are not bound to use these tags. You can style your own text to look the way you want using CSS.

[More about heading tags - Official Docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)

---

### Paragraphs 🐐

Simply add paragraphs using `<p> </p>` tag

```xml
<p>
    You can write a paragraph of text here.
</p>

<p>
    You can write another paragraph of text here.
</p>

<h3>
    Heading to the third paragraph
</h3>

<p>
    You can write third paragraph of text here.
</p>
```

**The Output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671727232382/a22d607c-9264-44b6-aec1-a312794efad3.png)

[Read more about paragraph tags - Official Docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)

---

### Formatting Tags 👑

Here are some tags you can use to give style to your text without adding CSS styling.

```xml
<b>1. This is shown bold</b>
<br>
<strong>2. This is shown strong</strong>
<br>
<i>3. This is shown italic</i>
<br>
<em>4. This is shown emphasized</em>
<br>
<mark>5. This is shown marked</mark>
<br>
<small>6. This is shown small</small>
<br>
<del>7. This is shown deleted</del>
<br>
<ins>8. This is shown inserted</ins>
<br>
<sub>9. This is shown subscript</sub>
<br>
<span>
    10. H<sub>2</sub>O
</span>
<br>
<sup>11. This is shown superscript</sup>
<br>
<span>
    12. a<sup>2</sup> + b<sup>2</sup> = c<sup>2</sup>
</span>
<br>
<u>13. This is shown underlined</u>
<br>
<code> 14. console.log("this is javascript code"); </code>
```

**The output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672037645783/d31ffb77-cf49-46b2-a753-4ef10e568992.png)

I have used `<br>` tags in between them to add line breaks.

If `<br>` tags were not used they would come in a single line because they are **inline** tags.

You can see **heading** and **paragraph** tags, they are in different lines irrespective of their content width because they are **block** tags. A block tag automatically adds a line break after their content.

[Read more about formatting tags on W3Schools](https://www.w3schools.com/html/html_formatting.asp)

---

### Block and Inline Tags 📦

You are now aware of what block and inline tags are.

Basically, **block-level tags** occupy the whole width of the screen. And the next tags are allowed to display in the next line.

And **inline-level tags** occupy the width equal to their size of content and allow the next tag to display after them in the same line.

[Read more about block-level element](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements)s and [inline-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements) - Official Docs

---

### HTML Entities 💎

There are entities to add spacing and symbols in HTML.

For example, `&nbsp;` adds space in the texts.

```xml
<p> It &nbsp; &nbsp; &nbsp; is &#160; unevenly &nbsp; &nbsp; spaced &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; sentence. </p>
```

**The output would be:**

`It       is unevenly     spaced           sentence.`

We cannot simply add spaces in our code without using `&nbsp;` or `&#160` .

> ⚡use preformatted tag &lt;pre&gt; if you want to display a sentence with line breaks, as you put them in code &lt;/pre&gt;
> 
> It prints texts as it is with spaces and line breaks in the code.

```xml
<p> 9 &gt; 6 &amp; 7 &lt; 8, and reward is &quot; &pound;1000 &quot;. </p>
```

**The output would be:**

`5 > 6 & 7 < 8, and reward is " £1000 ".`

**Here are some entities with their name and number:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672039197208/b62df98b-f4d2-46b4-bce5-27d3687824e6.png)

[checkout more about entities at w3Schools](https://www.w3schools.com/html/html_entities.asp).

**Q: Why do entities have names and numbers both?**

**A:** Browsers may not support all entity names, but the support for entity numbers is good.

---

### Here is an example to summarize this blog

```xml
<div>
    <h1>
        Water
    </h1>
    <h3>
        Introduction
    </h3>
    <p>
        <b> <i>Water </i> </b> is essential for <mark> survival </mark>. It               is a <del>  colorless </del> &nbsp; <ins> transparent </ins> and <u> odorless  </u> chemical substance ( <b>H<sub>2</sub>0</b> ) with  
<span>p<sup>H</sup> value 
      <b>
                <u>
                    <i>
                        7
                    </i>
                </u>
       </b>
 </span>
    </p>

    <h3>
        Properties
    </h3>
    <p>
        It have some properties like: <br>
        - It is a <b> liquid </b> at <b> room temperature </b> <br>
        - It is a <b> polar </b> molecule <br>
        - It is a <b> universal solvent </b> <br>

    </p>
</div>
```

**The output would be:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672041163597/e7bb50b2-2eba-4f88-ab13-5ba27ece7700.png)

---

### Exercises 🏹

Here are some **easy**, **to-the-point**, and **worth** practicing exercises on W3Schools.

* [Heading](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_headings1)
    
* [Paragraphs](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_paragraphs1)
    
* [Formatting](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_formatting1)
    

---

### Source Codes 💠

[Click here](https://github.com/WebD-Essentials/HTML5/archive/refs/heads/texts-headings-paragraphs.zip) to download the source code of this blog.

[Here is](https://github.com/WebD-Essentials/HTML5/tree/texts-headings-paragraphs) the source code of this blog on GitHub.

[Live Preview](https://webd-essentials.github.io/HTML5/texts-headings-paragraphs/) of the codes in this blog.

---

### Now it's your turn 🏌️

Try different combinations and write what's in your mind. In case of any questions, queries and doubts don't hesitate for a google search.

In the next blog, I will write about adding [images, icons, audio, videos, and various other visual media stuff on our webpage](https://webdessentials.hashnode.dev/images-audio-video-and-iframe-in-html).