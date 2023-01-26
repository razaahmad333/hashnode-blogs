# Let's use a js package 🎁

> 🚩 we would only discuss about javascript packages

## What is a package? 🤔

It is a piece of code written by some smart people which does something. If you want that functionality without writing all the code by yourself, you can use that particular package.

#### for example 🖊️

you are creating a website and at some point, you need to check if the email entered by the user is valid or not,  
You have two potential ways,

* either you write a function by yourself
    

```js
function isEmail(emailString) {
    // check for @ sign
    var atSymbol = emailString.indexOf("@");
    if(atSymbol < 1) return false;
    
    var dot = emailString.indexOf(".");
    if(dot <= atSymbol + 2) return false;
    
    // check that the dot is not at the end
    if (dot === emailString.length - 1) return false;
    
    return true;
}

isEmail('awe@some.com'); // => true
```

* or use a package
    

```js
var validator = require('validator');

validator.isEmail('awe@some.com'); //=> true
```

## How to start using a package? 🧑‍💻

#### Prerequisites

* [brief knowledge of javascript modules](https://ahmadrazakhan946.hashnode.dev/your-first-javascript-code-in-terminal)
    

Lets start from scratch 💫  

* Create a new folder `hello-packages` anywhere on your computer  
    
* Then open a terminal in that directory  
    
* run the command
    

```shell
npm init -y
```

* Now its time to install the package
    

```shell
  npm install validator
```

* create a file `index.js` and paste this code in that file
    

```js
const validator = require('validator');
console.log(validator.isEmail('some@thing.com'));
```

At this time, your directory should look like

```js
/**
* hello-packages
* -- node_modules
* -- index.js
* -- package-lock.json
* -- package.json
*/
```

* run the code inside `index.js` file
    

```shell
 node index.js
```

* output you will get is
    

```shell
true
```

[check this out](https://github.com/validatorjs/validator.js#validators) to explore more features and functionality that validator package can offer.

[check this out](https://blogs.m3rashid.in/the-packagejson) to know what a package.json file is

## Using a package in a project that doesn't use modules but static HTML files

you can use their cdn `https://unpkg.com/validator@latest/validator.min.js`

```html
<script src="https://unpkg.com/validator@latest/validator.min.js"></script>
```

Add a script tag in your HTML head with cdn url.

## How to check what features and functionality a package offer? 🪶

Most of them have great documentation.  
or you can check out their GitHub repositories.

## Who writes these packages? 🧠

Smart people like you and me.  
Most of the packages are free to install, and you can contribute to their GitHub repos.  

## What is npm?

npm stands for node package manager.  
It is a command line client. which means that you can use it to

* install a package `npm install validator`
    
* uninstall a package `npm uninstall validator`
    
* publish a package `npm publish`
    
* and a lot more `npm -h`
    

It is also an online database of public and paid-for private packages, called the [npm registry](https://www.npmjs.com/).

[Source code](https://github.com/razaahmad333/coding-challenges/tree/main/2022-08-30-hello-packages): All the codes used in this blog. 😊