# Your first Javascript code in terminal 😃

### Prerequisites 
* Node.js installed in your system [Nodejs website](https://nodejs.org/en/)
* [Here](https://youtu.be/3F5IaPqj7ds) is a mini tutorial on how to install Node.js in your system
* type ` node -v` in terminal to check if it is installed

### Lets write your first line of code
* open up your terminal
make a directory hello-modules
```shell
mkdir hello-modules
```
```shell
cd hello-modules
```
```shell
npm init -y
```

* it will generate a file named `package.json`
```json
{
  "name": "hello-modules",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

* now create two new files <br/>
first one -> `hello-modules/index.js`  <br/>
is it necessary to create a file with the same name  mentioned in package.json <br/> `"main": "index.js"` ?  NO. <br/>
If you are not going to publish it to npm using `npm publish` <br/>
This field `"main"` does not serve any purpose. <br/>
second one -> `hello-modules/universe.js` <br/>

* and your directory will look like <br/>
  ```js 
  /**
  * hello-modules
  * -- index.js
  * -- package.json
  * -- universe.js
  */
  ```

* write some code in   `hello-modules/index.js`
<br/>
```js
console.log('hello modules from index.js')
```
* then in terminal type
```shell
node index.js
```
*make sure your terminal is in current directory  ...\hello-modules>

* your terminal would give output 
```shell
hello modules from index.js
```
Woohoo, your javascript code now runs in the terminal.
> That's why Node.js® is called JavaScript runtime.

### Now its time for fancy stuffs like 
`module.exports` & `require()` 

Let me clear you a few things before we go ahead <br/>

When you start doing cool stuffs with javascript in terminal instead of browser.

you write javascript code in file like `index.js`, that file is known as a module.

Now there are two types of modules
* CommonJs module
* ECMAScript module 

by default node supports Commonjs module system
### What it feels like writing code in CommonJS module system
you can communicate between two files ( modules ) and use one another codes, functions, classes 
* go to `hello-modules/universe.js` <br/>
```js
// declare a const 
const milkyWay = " it has billions of stars "
// and export it with a magic spell
module.exports = milkyWay;
```

* in `hello-modules/index.js` <br/>
```js
// magic spell to get that const from another file (module)
// is to make that module (file) available in this file first
const milkyWaySomeWhereElse = require('./universe.js');
// now console it to terminal
console.log(milkyWaySomeWhereElse);
```
* now in terminal type
```shell
node index.js
```
* will give output like
```shell
 it has billions of stars 
```
> Congrats 🎉, You just used two magical spells `exports` and `require`

## Lets do some experiments 🧪
### Experiment  #1
* clear everything from `hello-modules/universe.js` & make it empty <br/>
and in `hello-modules/index.js` write 
```js
const milkyWaySomeWhereElse = require('./universe.js');
console.log(milkyWaySomeWhereElse);
```

* in terminal type
```shell
node index.js
```

* it will give output like
```shell
{}
```

### Experiment #2
* in `hello-modules/universe.js` write 
```js
const solarSystem = "It has a planet called Earth";
const pandora = "this planet exists in movie Avatar";
module.exports.solarSystem = solarSystem;
module.exports.pandora = pandora;
// you can remove module. from above lines
// exports.solarSystem = solarSystem;
// module.exports.pandora = pandora;
// they will work the same way
```

* then in `hello-modules/index.js` keep it same
```js
const milkyWaySomeWhereElse = require('./universe.js');
console.log(milkyWaySomeWhereElse);
```
* in terminal type
```shell
node index.js
```

* you will get an output
```shell
{
  solarSystem: 'It has a planet called Earth',
  pandora: 'this planet exists in movie Avatar'
}
```
#### from this experiment, what I conclude is <br/>
  * if we export from a module (file) like <br/>
  `module.exports.solarSytem = solarSystem` <br/>
  `module.exports.pandora = pandora` <br/>

  * and  require from another file (module) <br/>
   `const milkyWaySomeWhereElse = require('./universe.js')` <br/>
    we get an object with keys `pandora` and `solarSystem` <br/>
  * and we access them like we do with objects ([Associative Array](https://www.youtube.com/watch?v=_5jdE6RKxVk)) <br/>
    ```js      
    // either by dot Notation
       const pandora = milkyWaySomeWhereElse.pandora;
       const solarSystem = milkyWaySomeWhereElse.solarSystem;
    // or from bracket Notation
       const pandora =  milkyWaySomeWhereElse["pandora"];
       const solarSystem = milkyWaySomeWhereElse["solarSystem"];
    // or by destructuring assignment 
    // most popular one used in modules while importing
       const { pandora, solarSystem } = milkyWaySomeWhereElse;
    // most of the times you will see
       const { pandora, solarSystem } = require('./universe.js');
```


### Experiment #3
* in `hello-modules/universe.js` write
  ```js
  const solarSystem = "It has a planet called Earth";
  const milkyWay = " it has billions of stars "
  module.exports.solarSystem = solarSystem;
  module.exports =  milkyWay;
  ```
* keep `hello-modules/index.js` same
```js
const milkyWaySomeWhereElse = require('./universe.js');
console.log(milkyWaySomeWhereElse);
```

* in terminal type
```shell
node index.js
```
* the output you will get is
```shell
 it has billions of stars
```

#### from this experiment, what I conclude is 
* in `hello-modules/universe.js` <br/>
`module.exports =  milkyWay;` <br/>
only this line worked and milkyWay got exported

* whatever you put in place of milkyWay get exported as it is from that whole file (module), leaving other exports like `module.exports.solarSystem = solarSystem`
useless <br/>
* In above two experiments, we have seen a file (module) exports a object. <br/>
It is not always the case. <br/>
Experiment #1 and #2 were special cases. <br/>
* You can export anything from a module ( lets say from `hello-modules/universe.js` ) 
using `module.exports = anything`. <br/>
* And require ( import that module) from `hello-modules/index.js` like <br/>
```js
const milkyWaySomeWhereElse = require('./universe.js');
console.log(milkyWaySomeWhereElse);
```
<hr>

* in `hello-modules/universe.js` 
```js
module.exports = "you can export a string";
```
`milkyWaySomeWhereElse`  will be equal to `"you can export a string"` 
<hr>
```js
module.exports = ["an", "array", "with", 1, "boolean", "value", true];
```
now `milkyWaySomeWhereElse`  will be equal to `["an", "array", "with", 1, "boolean", "value", true]`
<hr>
```js
module.exports = {
sky:"it is blue",
hello:"you can export a object"
};
```
In this case `milkyWaySomeWhereElse` will be equal to <br/> 
`{
sky:"it is blue",
hello:"you can export a object"
}` 
<hr>
```js
module.exports = function(){
return "you can a export a function which returns some value";
}
// or
// module.exports = function(){
//  console.log("you can a export a function which do not returns any value");
// }
```
`milkyWaySomeWhereElse` is a function now <br/>
the function is declared only and get assigned to another variable, <br/>
but not called yet! <br/>
or not executed yet <br/>
This function is same as normal functions in javascript, <br/> 
to call or execute write </br> 
`milkyWaySomeWhereElse()` <br/>
`console.log(milkyWaySomeWhereElse())` will output the string <br/>
`"you can a export a function which returns some value"`

<hr>
* In `hello-modules/universe.js` you can export a class. <br/>
  ```js
  class Planet {
      constructor(name) {
        this.name = name;
    }

    getName() {
        return this.name;
    }

    sayHiTo(name) {
        console.log(`Hi ${name}, I'm ${this.name}`);
    }
}

  module.exports = Planet;
  ```

* from `hello-modules/index.js`  <br/>
    ```js
  const Planet = require('./universe.js');

  const mars = new Planet('Mars');

  console.log(mars.getName());
  mars.sayHiTo('Elon Musk');
    ```
* in terminal type
```shell
node index.js
```
* output would be like
```shell
Mars
Hi Elon Musk, I'm Mars
```
<hr>
## Its your turn 🎯
### [I have written a coding-challenge based on this topic.](https://github.com/razaahmad333/coding-challenges/blob/main/2022-07-06-hello-modules/question.md)
* Go ahead make modules ( javascript files ) and practice with this coding challenge. <br/>
* Do cool stuffs. </br>
* Happy Learning ! <br/>

> NOTE:  I will write about ECMAScript (ES6) modules in next post.

