# Forms and Input Elements in HTML 📄

In real life, forms are used to take information from the user/person. For example forms for job applications and entrance examinations.

**This is what form on a paper looks like:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673429223460/c7d1748a-77e1-44de-b042-bc20c58d4670.png)

Here, you will notice **blanks** that need to be filled with appropriate information.

So, for these **blanks**, there are **input elements** in HTML.

```xml
<input />
```

`input` tag is an inline-level tag.

**Here is how a form in HTML looks like**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673430890373/fe81155a-32e9-4ad0-90ce-f1761b1a581c.png)

### Various Input elements - Explained ⚙️

Information can be of various types. For example text, number, email address, password, date, time, etc.

* **For text 🔤**
    
    ```xml
    <input type="text" placeholder="please enter your name" >
    ```
    
* **For number 🔢**
    
    ```xml
    <input type="number" placeholder="please enter your age" >
    ```
    
* **For email address 📧**
    
    ```xml
    <input type="email" placeholder="please enter your email address" >
    ```
    
* **For password 🔑**
    
    ```xml
    <input type="password" placeholder="please enter your password" >
    ```
    
    > ⚡password and email are type of texts, so why HTML have different types for them?
    > 
    > The answer :
    > 
    > * type `password` hides the text you enter.
    >     
    > * type `email` performs check whether the text is email or not.
    >     
    
* **For date 📅**
    
    ```xml
    <input type="date" placeholder="please enter your dob" >
    ```
    
* **For time ⌚**
    
    ```xml
    <input type="time" placeholder="please enter sunrise time" >
    ```
    
* **For file 📁**
    
    ```xml
    <input type="file" >
    ```
    
* **For longer texts ( ex: feedback, or remarks) 📃**
    
    ```xml
    <textarea name="textarea" id="textarea" cols="30" rows="10">
    </textarea>
    ```
    
    > ⚡`cols` and `rows` are used set width and height of the container.
    
    [**Read more about input elements - Official Docs**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
    

### Elements/tags for Options

* **select**
    
    use `<select> </select>` tag, if you have a lot of options to select from:
    
    ```xml
    <label>Select:</label>
    <select>
        <option value="option1">Option 1</option>
        <option value="option2">Option 2</option>
        <option value="option3">Option 3</option>
        <option value="option4">Option 4</option>
        <option value="option5">Option 5</option>
    </select>
    ```
    
    **The preview:**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673433638028/23be0ebc-55ab-4d13-9bd5-cab5e03dda93.png)
    
    ---
    
* **type="radio"**
    
    use `input` element with `type="radio"` when you have fewer options and can easily be shown on screen without making the UI ( user-interface/screen) look ugly👍.
    
    ```xml
    <p>Gender</p>
    
    <input type="radio" name="gender" value="Male">
    <label>Male</label>
    <br>
    
    <input type="radio" name="gender" value="Female">
    <label>Female</label>
    <br>
    
    <input type="radio" name="gender" value="Other">
    <label>Other</label>
    <br>
    ```
    
    **The preview:**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673433729282/d84a5a18-ec71-456e-b95f-62cfc5fd6f44.png)
    
    > ⚡ All these input elements are connected to each other through `name` attribute. That's why you will notice them working as a system.
    
    ---
    
* **type="checkbox"**
    
    when you have fewer options and you want the user to select multiple options, you can use checkboxes.
    
    ```xml
    <p>Vehicles</p>
    
    <input type="checkbox" name="vehicle" value="Bike">
    <label> I have a bike</label><br>
    
    <input type="checkbox" name="vehicle" value="Car">
    <label> I have a car</label><br>
    
    <input type="checkbox" name="vehicle" value="Boat">
    <label> I have a boat</label><br>
    ```
    
    **The preview:**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673433790385/672c8da8-65e3-477c-8c1d-e1f67d90e81f.png)
    
    ---
    

### Complete code - for a form 💻

We need to wrap all the input elements inside `<form> </form>` tag like this

```xml
<form>
    <label for="name">Name:</label>
    <input 
        type="text" 
        id="name" 
        name="name" 
        placeholder="Enter your name" 
        required
    >
    <br>

    <label for="email">Email:</label>
    <input 
        type="email" 
        id="email" 
        name="email" 
        placeholder="Enter your email" 
        required
    >
    <br>

    <label for="password">Password:</label>
    <input 
        type="password"     
        id="password" 
        name="password"     
        placeholder="Enter your password" 
        required
    >
    <br>
    
    <input type="submit" value="Submit">
    <input type="reset" value="Reset">
</form>
```

**The preview:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673433848889/18097306-1a98-4650-be3b-5fdeb99be1ec.png)

**Attributes explained:**

* if `for` attribute in label tag is same as `id` attribute in input tag, then on clicking the label text on webpage corresponding input element get focused ( you will see an outline around that input element ).
    
* `required` attribute will not allow you to submit the form, if that corresponding input element is not filled.
    
* `placeholder` attribute is used to show helper message to the user.
    
* `name` attribute is used by backend developers to identify the information.
    
* `type="submit"` creates a button with `value` as its label. Form get submitted when this button is clicked.
    
* `type="reset"` also creates a button with `value` as its label. All the value is reset when this button is clicked.
    

[**Read more about Forms - Official Docs**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

---

### Why and how we use forms - a technical dive 🏊

Form is used to take information from the user.

The steps are:

1. Creating a form using HTML
    
2. Handling the form submission (when submit button is clicked) using javascript.
    
3. data is sent to the backend.
    
4. In the backend, we validate the data to determine if it is correct or not,
    
5. we send back errors to the frontend ( on the webpage ) if there are any
    
6. if the data is all correct, we store it in the database and send a success message to the frontend
    
7. and the frontend shows the user a **congratulations** message
    

**🚩 We will be learning more about forms and data in JAVASCRIPT.**

> ⚡ There are no hard and fast rules in design. Observe everything and design your own way through it.

---

### Exercises 🏌️

Here are some **free** and **worth practicing** exercises on w3schools.

* [Input types](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_form_input_types1)
    
* [Input Attributes](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_form_attributes1)
    
* [Form Elements](https://www.w3schools.com/html/exercise.asp?filename=exercise_html_form_elements1)
    

---

### Source codes

* [Download](https://github.com/WebD-Essentials/HTML5/archive/refs/heads/forms-and-input-elements.zip) the source code of this blog
    
* [Check out](https://github.com/WebD-Essentials/HTML5/tree/forms-and-input-elements) the source code on GitHub.
    
* [Preview](https://webd-essentials.github.io/HTML5/forms-and-input-elements) the output of this blog.
    

In the next blog, I will be making a simple project using HTML5 to summarize this whole blog-series.