Image to ASCII
==============

Node.js module that converts an image to ASCII art.

## How to use

First download and install [ImageMagick](http://www.imagemagick.org/). In Mac OS X, you can simply use [Homebrew](http://mxcl.github.io/homebrew/) and do:

    brew install imagemagick

### Constructor: `new ImageToAscii (options)`
`options` is an object containing the following fields:
 - `pixels`: string representing the *ASCII pixels* in the brightness order. If not provided, the default value will be used: `" .,:;i1tfLCG08@"`
 - `multiplyWidth`: the width of the ASCII pixles. For keeping the aspect ratio in terminal, the default value is `2`
 - `reverse`: boolean value that indicates if the `pixels` value must be reversed. Default is `undefined`.
 - `colored`: boolean value that indicates if the ASCII art must be colored or not. Default is `undefined`.

### `.convert (imagePath, callback)`
 - `imagePath`: the path to the PNG image
 - `callback`: the callback function

## Example

```js
var ImageToAscii = require ("../index")
  , myImage = new ImageToAscii ({
        resize: {
            height: "100%"
          , width:  "50%"
        }
      , multiplyWidth: 1
      , colored: true
    })
  ;

myImage.convert(__dirname + "/octocat.png", function(err, converted) {
    console.log(err || converted);
});
```
[Baracktocat](https://octodex.github.com/baracktocat/) + `image-to-ascii` = Nice ASCII art :smiley:


## Test

> [![](http://i.imgur.com/piG4iMu.png)](https://asciinema.org/a/8881)


## Changelog

### `v0.1.1`
 - Added support for images from Internet

### `v0.1.0`
 - Initial version

## License
See LICENSE file
