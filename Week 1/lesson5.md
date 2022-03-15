# Node File System

The node file system is an inbuilt module tah handles operations like creating, reading, updating and deleting files.    


All file system operations come in both synchromnous and asynchronous forms.   


To make us of the file system module you import it  with




```javascript

let fs = require("fs");

```

### Example of the Asynchronous for of file system

```javascript

var fs = require("fs");

// Asynchronous read
fs.readFile('input.txt', function (err, data) {
if (err) {
	return console.error(err);
}
console.log("Asynchronous read: " + data.toString());
});

```


### Example of the Synchronous for of file system

```javascript

var fs = require("fs");

// Synchronous read
var data = fs.readFileSync('input.txt');
console.log("Synchronous read: " + data.toString());

```
