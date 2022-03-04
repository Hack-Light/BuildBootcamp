# **Node Module System**

Node.js provides an environment outside of the browser for executing javascript code.

A typical node.js application is normally full of features that would require lots of logics, which will lead to many function for reusability. 

To keep our project organised and maintainable, we split our whole project into into small piece files that have specific purpose. This small piece of files are called `Modules` and they can be imported where they are needed.

Understanding how modules work is very important as a node.js developer because node.js operates a module system which makes it easy for developers to separate out your code logic which can be reused.

## **Node Module System Architecture**

In the Node.js module system, each file is treated as a separate module and before each module is ran/executed wrapped with a function which gives you access to variables like `exports`, `__filename`, `require`, etc.

It is important to note that variables in modules are not globally scoped rather they are locally scooped, which mean module A can not access variables in module B except the variable was exported.

The function look like this

```javascript 
function(exports, require, module, __filename, __dirname) {
  // module code goes in here
}
```


## **The uses of the variables exposed by the module function**

### **require**  

Allows for a module to import other modules.
example

```javascript

let path = require("path")

let myModule = require("./mymodule.js")

let { java, python } = require("./module/exist/somwhere.js")

```

### **exports and module** 

makes it possible to export a modules.
example


```javascript
// default export
module.exports = function defaultExportedFunction () {
   
}

// named export

module.exports = {
    something,
    anotherSomething
}

exports.exportFunc = () => {}

```


***

## *Extra Resources*
https://www.codementor.io/@oparaprosper79/node-js-module-system-15r2ud9v1c

