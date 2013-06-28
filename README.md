# getScreenMedia

## What is this?

A tiny browser module that gives us a simple API for getting access to a user's screen. It uses https://github.com/HenrikJoreteg/getUserMedia's API.

It gives us a cleaner node.js-style, error-first API and cross-browser handling. No browser support checking necessary, lack of support is treated in the same way as when the user rejects the request: the callback gets passed an error as the first argument.

Suitable for use with browserify/CommonJS on the client. 

If you're not using browserify or you want AMD support use `getscreenmedia.bundle.js`.


## Installing

```
npm install getscreenmedia
```

## How to use it


With this helper it's clean/simple to get access to a user's camera, mic, etc.

```js
var getUserMedia = require('getscreenmedia');

getscreenmedia(function (err, stream) {
    // if the browser doesn't support user media
    // or the user says "no" the error gets passed
    // as the first argument.
    if (err) {
       console.log('failed');
    } else {
       console.log('got a stream', stream);  
    }
});
```


## Why?

It's ugly and annoying to check for support without this tool. Node-style (error-first) APIs that are cross-browser, installable with npm and runnable on the client === win!


## License

MIT

## Created By

If you like this, follow: [@HenrikJoreteg](http://twitter.com/henrikjoreteg) on twitter.
