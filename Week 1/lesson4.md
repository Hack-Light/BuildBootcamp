## **Node.js Path Module**

Node.js gives us path module that helps you interact with file paths.

Path is a core module in Node, which means you can use it without installing. It also has useful properties and method that helps you work with the file system.

You can import path module using

```javascript
const path = require('path');
```

Some Useful path properties and methods

```javascript
    path.basename(path, [,ext])
    path.dirname(path)
    path.extname(path)
    path.format(pathObj)
    path.isAbsolute(path)
    path.join(...path)
    path.normalize(path)
    path.parse(path)
    path.relative(from, to)
    path.resolve(...path)
    path.sep
    path.delimiter
```


## `path.basename()`

The method path.basename() returns the last part of a specified path. This includes the filename and the file extension

It takes two parameters. The file path (which is required).

Example.

```javascript

let result = path.basename('/public_html/home/index.html');
console.log(result);

```

Output
```console.log
index.html
```

In a situation where you want to filter out only specific extensions, you can use the second parameters 

```javascript
let result = path.basename('/public_html/home/index.html','.html');
console.log(result);
```

Output

```console.log
index
```

## `path.dirname(path)`

The `path.dirname()` returns the directory name of a specified path. Example

```javascript
let result = path.dirname('/public_html/home/index.html');
console.log(result);
```

Output
```console.log
/public_html/home
```

## `path.extname(path)`

This method return the extension of the specified path. Example
```javascript
console.log(path.extname(‘custom.html'));
console.log(path.extname('app.js'));
console.log(path.extname(‘readme.md'));
```

Output

```console
.html
.js
.md
```

## `path.join()`

This method joins a sequence of specified path segments, normalises the resulting path and returns it. Example


```javascript
let pathToDir = path.join('/home', 'js', 'dist', 'app.js');
console.log(pathToDir);
```

Output

```console.log
\home\js\dist\app.js
```

The path object has the sep property that represents the platform-specific path separator:
`path.sep`

```
path.sep
```

The path.sep returns \ on Windows and / on Linux and macOS.

The path object also has the delimiter property that represents the path delimiter:
`path.delimiter`

```
path.delimiter
```

The path.delimiter returns ; on Windows and : on Linux and macOS.

## **Summary**

Node.js applications can require working on files and the path module make it very easy for use to access and work with file paths.

## *More Reading*

https://www.javascripttutorial.net/nodejs-tutorial/nodejs-path-module/#:~:text=in%20Node.js-,Node.,paths%20in%20the%20file%20system.

