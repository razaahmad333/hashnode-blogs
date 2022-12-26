# Let's explore ES6 modules 😃

### Prerequisites 🦿
* Node.js installed in your system [Nodejs website](https://nodejs.org/en/)
* [Here](https://youtu.be/3F5IaPqj7ds) is a mini tutorial on how to install Node.js in your system
* type ` node -v` in terminal to check if it is installed

## What are modules and what are commonjs and es6 modules 🤔

When you start doing cool stuffs with javascript in terminal instead of browser.

you write javascript code in file like `index.js`, that file is known as a module.

Now there are two types of modules
* CommonJs module
* ECMAScript ( es6) module 

[we have already discussed about default module environment provided by nodejs -> commonjs](https://ahmadrazakhan946.hashnode.dev/your-first-javascript-code-in-terminal)

### Lets write some code and discuss es6 modules 🧑‍💻
* open up your terminal
make a directory hello-es6-modules
```shell
mkdir hello-es6-modules
```
```shell
cd hello-es6-modules
```
```shell
npm init -y
```

* it will generate a file named `package.json`
```json
{
  "name": "hello-es6-modules",
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

* now create two new files  <br/>
first one -> `hello-es6-modules/index.js`  <br/>
is it necessary to create a file with the same name  mentioned in package.json <br/> `"main": "index.js"` ?  NO. <br/>
If you are not going to publish it to npm using `npm publish` <br/>
This field `"main"` does not serve any purpose. <br/>
second one -> `hello-es6-modules/oceans.js` <br/>

* and your directory 📁 will look like <br/>
  ```js 
  /**
  * hello-es6-modules
  * -- index.js
  * -- package.json
  * -- oceans.js
  */
  ```

## Lets activate es6 module environment 🏞️
* edit your `package.json`  and add the line ` "type":"module" `
```json
{
  "name": "hello-es6-modules",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "type": "module",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

### Come on! lets write some code for real 👨‍💻👩‍💻

* in `hello-es6-modules/oceans.js` write the code
```js
const seahorse = 'It is a Seahorse';
export default seahorse;    
```

* in `hello-es6-modules/index.js`  write
```js
import oceansFromNowhere from './oceans.js'
console.log(oceansFromNowhere)
```

* to run the code in `hello-es6-modules/index.js`, who is ready to console.log | print | give output. <br/>  In terminal type
```shell
node index.js
```

* you will get the output
```shell
It is a Seahorse
```

> #### the above program was the example of " default export "

### In es6 module, there are two types of exports
* default export  ( the above example )
* named export

#### So lets see named export 

* in `hello-es6-modules/oceans.js` clear up everything and write the code <br/>
    ```js
    const shell = "I live in the ocean";

    // you can export like this
    export const fish = "I am a fish";

    // and also like this too
    export { shell };

    // both exports works the same way
    ```

* in `hello-es6-modules/index.js` <br/>
    ```js
    import { shell, fish } from './oceans.js';

    console.log(shell);
    console.log(fish);
    ```

* in terminal type 
    ```shell
node index.js
    ```
* the output you will get
    ```shell
I live in the ocean
I am a fish
    ```

#### An example of module containing both named and default export

* in `hello-es6-modules/oceans.js` clear up everything and write the code <br/> 
   ```js
   const shell = "I live in the ocean";

   export const fish = "I am a fish";

   export { shell };

   const king = "I am the king of the ocean";

   export default king;
    ```

* in `hello-es6-modules/index.js` <br/>
    ```js
    import TheKiNg from './oceans.js';
    import { shell, fish } from './oceans.js';
   
    // or you can import with one line
    // import TheKiNg, { shell, fish } from './oceans.js';

    console.log(shell)
    console.log(fish)
    console.log(TheKiNg)
    ```

* in terminal type 
    ```shell
node index.js
    ```
* the output you will get
    ```shell
I live in the ocean
I am a fish
I am the king of the ocean
    ```

### Lets discuss the difference between default and named export
#### the default export
* you export with statement like `export default king;` from a module
* and you can import it in another module using any name <br/> `import TheKiNg from './oceans.js'`
* you cannot use ` as ` statement
* you cannot have multiple default export from a module ( aka file )

#### the named export
* you export like <br/>`export const fish;` <br/> ` export function sayHello(){ }` <br/>
* and import it with that exact name in another module, <br/> by destructuring assignment which seems to be object destructuring assignment but they are different.<br/> 
`import { fish, sayHello } from './oceans.js'` <br/>
  to escape from namespace you can use ` as ` <br/>
`import { fish as waterFish , sayHello } from './oceans.js'` 
* you can have multiple named export from a file ( aka module )


## Examples 🧪
### you can default export without name
* you can import the same way in all cases of this example.  <br/> from `hello-es6-modules/index.js` with the statement
```js
import isStrange from './oceans.js';
```

#### string
* in `hello-es6-modules/oceans.js` to export write
```js
export default "this is not strange";
// export default  const strange = "this is not strange";     not allowed
```

#### functions
* in `hello-es6-modules/oceans.js` to export type  <br/> with function expression 
  ```js
  export default function () {
      return 'I am river';
  }

  // allowed 
  //  export default function river () {
  //  return 'I am river';
  // }

  ```
with arrow functions
  ```js
    export default () => {
      return 'I am river';
    }

  // not allowed
  //    export default const river = () => {
  //      return 'I am river';
  //    }
  
  // or 
  // export default () => "I am river";
  ```

#### classes 
  * in `hello-es6-modules/oceans.js` to export type 
    ```js
      export default class {
            constructor() {
               this.name = 'ocean';
            }
            say() {
               return `I am ${this.name}`;
            }
      }

     // allowed
     // export default class Ocean {
     //    constructor() {
     //       this.name = 'ocean';
     //    }
     //    say() {
     //      return `I am ${this.name}`;
     //    }
     // }
 ```

> you can use names too. If you want 

### [Checkout this link for more example on this topic](https://github.com/razaahmad333/coding-challenges/tree/main/2022-07-09-es6-modules/example)
### [Checkout this link for coding challenge on this topic](https://github.com/razaahmad333/coding-challenges/blob/main/2022-07-12-es6-modules/question.md)

* Try mixing 🧫🧪 basic javascript and make new things.
* Remember "There is no science without experiments 🥼".