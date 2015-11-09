# msg2img
A JavaScript browser module for encoding arbitrary data into a PNG image


## Build
*NOTE:* The module in msg2img.js is ready to be used in RequireJS environments. If you want to use it without an AMD capable system, use the msg2img_standalone.js file and load it via `<script>` tag.

The standalone module was built using browserify as follows:

```bash
npm install browserify
browserify -e msg2img.js -s msg2img -o msg2img_standalone.js
```

## Usage
Please note that the `encode` function takes an `ÀrrayBuffer` object and returns the data URL of the generated PNG image. The `decode` function works just the other way around.

```bash
var msg2img = require("msg2img");
var msg = "Hello there, I am in the image!";
var msgArr8 = new Uint8Array(msg.length);
for (var i = 0; i < msg.length; i ++)
  msgArr8[i] = msg.charCodeAt(i);
var imgDataURL = msg2img.encode(msg);
msgArr8 = new Uint8Array(msg2img.decode(msgDataURL));
msg = msgArr8.apply(null, String.fromCharCode);
```

## Tests
Coming soon. For now, just read the sources, they are short and easy to understand.
