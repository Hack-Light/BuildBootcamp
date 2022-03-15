# Node HTTP Module

Servers are all about handling requests. It can be recieving request from the client, sending response back to the client or sending a request to another server.    


In native javascript request can be sent or handled with `fetch` or `axios` but node.js provides us with a module to handle requests. 


To make use of the file system module you import it  with




```javascript

let https = require("https");

```

### Example of the GET request with axios

```javascript

const axios = require('axios')

axios
  .get('https://example.com/todos')
  .then(res => {
    console.log(`statusCode: ${res.status}`)
    console.log(res)
  })
  .catch(error => {
    console.error(error)
  })


```
### Example of the GET request with node.js http module

```javascript

const https = require('https')
const options = {
  hostname: 'example.com',
  port: 443,
  path: '/todos',
  method: 'GET'
}

const req = https.request(options, res => {
  console.log(`statusCode: ${res.statusCode}`)

  res.on('data', d => {
    process.stdout.write(d)
  })
})

req.on('error', error => {
  console.error(error)
})

req.end()


```


### Example of the POST request with axios

```javascript

const axios = require('axios')

axios
  .post('https://whatever.com/todos', {
    todo: 'Buy the milk'
  })
  .then(res => {
    console.log(`statusCode: ${res.status}`)
    console.log(res)
  })
  .catch(error => {
    console.error(error)
  })


```

### Example of the POST request with node.js module

```javascript

const https = require('https')

const data = JSON.stringify({
  todo: 'Buy the milk'
})

const options = {
  hostname: 'whatever.com',
  port: 443,
  path: '/todos',
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Content-Length': data.length
  }
}

const req = https.request(options, res => {
  console.log(`statusCode: ${res.statusCode}`)

  res.on('data', d => {
    process.stdout.write(d)
  })
})

req.on('error', error => {
  console.error(error)
})

req.write(data)
req.end()

```





There is more to http module than i have outlined here. We will see more as we progress but feel free to always source for knowledge.



## *Extra Resources*
> https://nodejs.org/api/https.html


> https://github.com/Hack-Light/wejapa-week-1/blob/master/server.js
