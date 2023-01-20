# Lists in HTML 🍡

There are a lot of real-life examples that need to be presented in a list or tabular form.

In this blog, we will be exploring the syntax of Lists in HTML5.

**There are two types of lists to use in HTML:**

* Ordered list ( arranged with numbers or alphabets ).
    
* Unordered list ( presented with bullet points or discs ).
    

### Ordered List `<ol> </ol>`

An ordered list is wrapped inside `<ol> </ol>` tag and items are added using `<li> </li>` tag.

In this code, I have used a header tag `<h2> </h2>` to give this list a heading ( not mandatory ).

**Here is the code for the ordered list**:

```xml
<h2>The Forbes 2022</h2>
<ol>
    <li>
        Elon Musk. $219 B. United States.
    </li>
    <li>
        Jeff Bezos. $171 B. United States.
    </li>

    <li>
        Bernard Arnault & family. $158 B. France.
    </li>
    <li>
        Bill Gates. $129 B. United States.
    </li>
</ol>
```

**The Output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672125288509/6da74fcc-d55d-4318-b336-f094e2f5e8fa.png)

**You can change the numbering type of the ordered list**. For example:

```xml
<h2>The Forbes 2022</h2>
<ol type="i">
    <li>
        Elon Musk. $219 B. United States.
    </li>
    <li>
        Jeff Bezos. $171 B. United States.
    </li>

    <li>
        Bernard Arnault & family. $158 B. France.
    </li>
    <li>
        Bill Gates. $129 B. United States.
    </li>
</ol>
```

**The Output**: now, the numbering is in roman numbers

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672126867807/d581e78e-e419-422d-bdac-0d83cf414c5d.png)

Various types of numbering for ordered lists are:

* type="1" means ( 1, 2, 3, 4, 5...), it is by default ( means it comes automatically without assigning )
    
* type="a" means ( a, b, c, d, e...)
    
* type="i" means ( i, ii, iii, iv, v...)
    

[Checkout the official docs for more information on the ordered list](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)

> ⚡you can also assign different numbering type to each individual list item
> 
> ex: `<li type="a" > some list item </li>`

---

### Unordered List `<ul> </ul>`

```xml
<h2>Wonders of Our Universe</h2>
<ul>
    <li>
        Enceladus' geysers
    </li>
    <li>
        Rings of Saturn
    </li>
    <li>
        Jupiter's Great Red Spot
    </li>
    <li>
        the Asteroid Belt
    </li>
    <li>
        Mars' Olympus Mons
    </li>
    <li>
        Surface of the Sun
    </li>
    <li>
        Earth
    </li>
</ul>
```

**The output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672129047320/03e29d49-4c10-4af3-811f-7d044f56fca9.png)

**Numbering types in the unordered list are:**

* type="disc"
    
* type="circle"
    
* type="square"
    
* type="none"
    

**For example:**

```xml
<h2>Wonders of Our World</h2>
<ul type="circle">
    <li>
        The Great Barrier Reef
    </li>
    <li>
        The Grand Canyon
    </li>
    <li>
        The Amazon Rainforest
    </li>
    <li>
        The Sahara Desert
    </li>
    <li>
        The Himalayas
    </li>
</ul>
```

**The output would be :**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672129745726/32ddd197-6f5b-4a33-b486-b0af22746ec5.png)

[Checkout the official docs for more information on the unordered list](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)

---

### Nested lists 🪢

Lists inside a list.

You can put one list into another.

**The code:**

```xml
<h2>World</h2>
<ol>
    <li>
        <span> Asia </span>
        <ul>
            <li>
                India
                <ol type="none">
                    <li>
                        Delhi
                        <ul>
                            <li> Connaught Place </li>
                            <li> Chandni Chowk </li>
                            <li> Karol Bagh </li>
                            <li> Janpath </li>
                        </ul>
                    </li>
                    <li>
                        Mumbai
                    </li>
                    <li>
                        Kolkata
                    </li>
                    <li>
                        Chennai
                    </li>
                </ol>
            </li>
            <li>
                Japan
                <ol>
                    <li>
                        Tokyo
                    </li>
                    <li>
                        Yokohama
                    </li>
                    <li>
                        Osaka
                    </li>
                    <li>
                        Nagoya
                    </li>
                </ol>
            </li>
        </ul>
    </li>
    <li>
        <span>Europe</span>
        <ul type="none">
            <li>
                Germany
                <ol>
                    <li>
                        Berlin
                    </li>
                    <li>
                        Hamburg
                    </li>
                    <li>
                        Munich
                    </li>
                    <li>
                        Cologne
                    </li>
                </ol>
            </li>
            <li>
                France
                <ol>
                    <li>
                        Paris
                    </li>
                    <li>
                        Marseille
                    </li>
                    <li>
                        Lyon
                    </li>
                    <li>
                        Toulouse
                    </li>
                </ol>
            </li>

        </ul>
    </li>
    <li>
        <span>Africa</span>

    </li>
    <li>
        <span>America</span>
    </li>
</ol>
```

**The output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672132873820/61a9ad02-e6ca-438e-a873-ebee22cdb015.png)

---

### Definition Lists `<dl> </dl>`

If you have a term and its description and you want to display them something like this without doing CSS styling.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672379716946/c577441b-1727-4dd6-836c-7185f96d2aa0.png)

Use `<dl> </dl>` tag\*\*,\*\* the code for the above is:

```xml
 <dl>
            <dt>
                <h3>HTML</h3>
            </dt>
            <dd>
                Hyper Text Markup Language, the language of the web that is used to create web pages.
            </dd>
            <dt>
                <h3>CSS</h3>
            </dt>
            <dd>
                Cascading Style Sheets, the language of the web that is used to style web pages.
            </dd>
            <dt>
                <h3>JS</h3>
            </dt>
            <dd>
                JavaScript, the language of the web that is used to make web pages interactive.
            </dd>
        </dl>
```

**Understanding the above code:**

To create a definition list, wrap the pairs of `<dt></dt>` and `<dd></dd>` in `<dl> </dl>` tag.

* add the term using `<dt> </dt>` tag and
    
* description for that using `<dd> </dd>` tag.
    

[Description list - official docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl)

---

### Exercise 🏌️

* [Practice LIST exercises on W3Schools](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_lists1), here are some **easy** and **to-the-point** questions **worth** practicing for **FREE**.
    
* [w3c schools HTML playground](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_lists_nested): try editing and copy-pasting codes from here to there and see output instantly.
    

---

### Source Codes 💠

* [Download](https://github.com/WebD-Essentials/HTML5/archive/refs/heads/lists.zip) the source code of this blog.
    
* [Codes used in this blog on GitHub](https://github.com/WebD-Essentials/HTML5/tree/lists/lists/index.html).
    
* [Preview](https://webd-essentials.github.io/HTML5/lists) of the codes used in this blog.
    

In the next blog, I will be writing about [Tables in HTML](https://webdessentials.hashnode.dev/tables-in-html).