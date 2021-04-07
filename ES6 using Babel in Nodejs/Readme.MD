Hi all 🤞🤞<br/ >
In this short article, Today we will be learning about How to use ES6 syntax(like import from, export default, etc..) with NodeJs.<br />
To use these ES6 syntaxes in node we will use [**Babel**](https://babeljs.io/). Now You are thinking what the heck is babel??<br />
**Babel** is a toolchain that is mainly used to convert ECMAScript 2015+ code into a backward-compatible version of JavaScript in current and older browsers or environments. <br />
To understand what is babel and how to set it up I am taking a very simple example. You can use this setup for any NodeJs application(eg. for backend servers)

##  Prerequisites <br />
1. Must have Nodejs installed on your pc.
2. an editor of your choice. I prefer VSCode


### Let's start with the setup

First of all, create a folder
or 
on terminal write these command
> $ mkdir node_babel  

> $ cd node_babel



## Getting Started

In this blog, we will create a very simple add function(sum.js) and export it in the main function(index.js)

To initialize the project 

> $ npm init   <br/>

this will create a **package.json** file for you

Now create two files **sum.js** and **index.js**

> $ touch sum.js index.js

## Install required Dependencies

Now we will install babel 

> $ npm install --save-dev  @babel/core  @babel/cli  @babel/preset-env @babel/node


--save-dev as it is a development dependency


![folder structure](https://cdn.hashnode.com/res/hashnode/image/upload/v1616859773685/pFfcuCx7a.png)
*Folder Structure*


Let's understand about the following packages

1. [**@babel/cli**](https://babeljs.io/docs/en/babel-cli) :- It is a built-in CLI that can be used to compile files from the 
 command line.<br/>
2. ***@babel/node*** :- babel-node is a CLI that works exactly the same as the Node.js CLI, with the added benefit of compiling with Babel presets and plugins before running it.
<br/>
3. ***@babel/preset-env*** :- @babel/preset-env is a smart preset that allows you to use the latest JavaScript without needing to micromanage which syntax transforms (and optionally, browser polyfills) are needed by your target environment(s).<br/>

Now also install nodemon as a development dependency

> $ npm i --save-dev nodemon

After all these steps our package.json file looks like this 

![carbon (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1616862466740/jce0uGLco.png)


Now create a file `.babelrc` and put the following code in it.

```
{
  "presets": [
    "@babel/preset-env"
  ]
}
```

Now create an add function in `sum.js` file and default export that function

```
//sum.js
function add(a, b) { 
  return a + b;
}

export default add; // ES6 export

```

Now  in `index.js` import the add function and call it with the arguments
```
//index.js
import add from "./sum"; //ES6 import

console.log(add(3, 4)); //This should print 7 in the console

```

To run this code using babel we have to add scripts in the `package.json` file

```
"start": "nodemon --exec node_modules/.bin/babel-node index.js"
```
Now on the command line run the following command

> $ npm start

in console, you will get this

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1616862667496/FvTqVs_84.png)

Voilà  `:smiley:` . Now if you have come to the end Congratulations you completed the nodejs + Babel Setup

I hope you find this blog useful. Do let me Know your Thoughts.
