# Tables in HTML 🧱

Tables on a webpage can be used to display data in an organized format.

In HTML, the fundamental unit of a table is a cell.

And cells are grouped into rows.

A table can have `head` `body` and `foot` .

> ⚡ In this blog, live preview of every code is given. Make sure to [download](https://github.com/WebD-Essentials/HTML5/archive/refs/heads/tables.zip) the codes used in this blog and try to tweak them by your own. You can also use [W3Schools Tryit Playground](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_basic).

### The code for a typical table in HTML `<table> </table>`

```xml
<table>
    <thead>
        <tr>
            <th>First Name</th>
            <th>Last Name</th>
            <th>Marks</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>John</td>
            <td>Doe</td>
            <td>34</td>
        </tr>
        <tr>
            <td>Jane</td>
            <td>Doe</td>
            <td>24</td>

        </tr>
        <tr>
            <td>John</td>
            <td>Smith</td>
            <td>20</td>
        </tr>
        <tr>
            <td>Jane</td>
            <td>Smith</td>
            <td>25</td>
        </tr>

    </tbody>
    <tfoot>
        <tr>
            <td colspan="2">Total</td>
            <td>113</td>
        </tr>
    </tfoot>
</table>
```

**The output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672806017326/8c7ba1dd-c4b8-4999-b590-0fca9d6edbb7.png)

### The breakdown of the above code 🔯

All the code to create a table is wrapped inside `<table> </table>` tag.

This parent table tag can have three children `<thead> </thead>`, `<tbody> </tbody>` and `<tfoot> </tfoot>`.

Basically, these children tags of the table are rows or groups of rows.

And a row is created using `<tr> </tr>` tag.

And a row consists of cells.

A cell can be created using

* `<th> </th>` tag, if bold text ( something like a heading is required ).
    
* `<td> </td>` tag, if normal text is required.
    

---

### Useful attributes

* `border` , adds a border around the table and all of its cells. Further styling can be done using CSS.
    
    ```xml
    <table border="1">
        ...
    </table>
    ```
    
* `cellspacing` gives spacing between cells and `cellpadding` adds spacing inside each cell.
    
    ```xml
    <table border="1" cellspacing="10" cellpadding="10">
        ...
    </table>
    ```
    
    [Check out the live effect of the above code](https://webd-essentials.github.io/HTML5/tables#withAttr)
    
    **The output:**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1672890724977/1f5178e4-37dc-4178-896e-fe9b9d7cdfba.png)
    

---

### Colspan and Rowspan

They are the attributes given to cells `<td> </td>` and `<th> </th>` .

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673084920538/8b6675fc-738f-42fa-b5b2-0e7f603f9268.png )

* **Colspan** expands a particular cell by a given unit horizontally. It shifts the next cell in front of it. ( So, in this code I have not added any cell next to it ).
    
    ```xml
    <h2 id="withColspan2">A table with a colspan of 2 in of its cell</h2>
    <table border="1" cellpadding="20">
        <tr>
            <td>1</td>
            <td>2</td>
            <td>3</td>
        </tr>
        <tr>
            <td>4</td>
            <td colspan="2">5 &emsp;&emsp;6 </td>
            <!-- <td>6</td> -->
        </tr>
        <tr>
            <td>7</td>
            <td>8</td>
            <td>9</td>
        </tr>
    </table>
    <hr>
    
    <h2 id="withColspan3">A table with a colspan of 3 in of its cell</h2>
    <table border="1" cellpadding="20">
        <tr>
            <td>1</td>
            <td>2</td>
            <td>3</td>
        </tr>
        <tr>
            <td colspan="3">4 &emsp;&emsp; 5 &emsp;&emsp; 6</td>
            <!-- <td>5</td> -->
            <!-- <td>6</td> -->
        </tr>
        <tr>
            <td>7</td>
            <td>8</td>
            <td>9</td>
        </tr>
    </table>
    ```
    
    [Check out the live effect of the above code](https://webd-essentials.github.io/HTML5/tables#withColspan2)
    
    > ⚡`&emsp;` is used to give spacing.
    
* **rowspan** expands a particular cell by a given unit vertically. It shifts the next cell below it. ( So, in this code I have not added any cell below it ).
    
    ```xml
    <h2 id="withRowspan2">A table with a rowspan of 2 in of its cell</h2>
    <table border="1" cellpadding="20">
        <tr>
            <td>1</td>
            <td>2</td>
            <td>3</td>
        </tr>
        <tr>
            <td>4</td>
            <td rowspan="2">5 <br><br><br> 8</td>
            <td>6</td>
        </tr>
        <tr>
            <td>7</td>
            <!-- <td>8</td> -->
            <td>9</td>
        </tr>
    </table>
    <hr>
    
    <h2 id="withRowspan3">A table with a rowspan of 3 in of its cell</h2>
    <table border="1" cellpadding="20">
        <tr>
            <td>1</td>
            <td rowspan="3">2 <br><br><br> 5 <br><br><br> 8</td>
            <td>3</td>
        </tr>
        <tr>
            <td>4</td>
            <!-- <td>5</td> -->
            <td>6</td>
        </tr>
        <tr>
            <td>7</td>
            <!-- <td>8</td> -->
            <td>9</td>
        </tr>
    </table>
    ```
    
    [Check out the live effect of the above code](https://webd-essentials.github.io/HTML5/tables#withRowspan2)
    

Check the [source code](https://github.com/WebD-Essentials/HTML5/archive/refs/heads/tables.zip) and [live preview](https://webd-essentials.github.io/HTML5/tables/) for more experiments I have done on tables.

[Read more about tables - Official Docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)

---

### Exercises 🏌️

Here are some **easy and worth practicing** exercises on w3Schools.

* [tables](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_tables1)
    

---

### Source Codes 💠

* [**Click here**](https://github.com/WebD-Essentials/HTML5/archive/refs/heads/tables.zip) to download the source code of this blog.
    
* [**Here is**](https://github.com/WebD-Essentials/HTML5/tree/tables) the source code of this blog on GitHub.
    
* [**Live Preview**](https://webd-essentials.github.io/HTML5/tables/) of the codes in this blog.
    

In the next blog, I will be writing about [anchor tags `<a href="https://google.com"> Click here </a>`](https://webdessentials.hashnode.dev/links-and-navigation-in-html) .