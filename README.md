# base64 (npm @devtea2028/libero-illo-commodi-velit)

[![Build Status](https://travis-ci.org/devtea2028/libero-illo-commodi-velit.svg?branch=master)](https://travis-ci.org/devtea2028/libero-illo-commodi-velit)
[![Coverage Status](https://coveralls.io/repos/github/devtea2028/libero-illo-commodi-velit/badge.svg?branch=master)](https://coveralls.io/github/devtea2028/libero-illo-commodi-velit?branch=master)

**Disclaimer: For node versions < 4 use the 1.2.0 version.**

This modules can be used to encoding & decoding messages (strings) and files using base64.

I'm trying to add new features based on other packages to get an all in one npm module.
Actually **@devtea2028/libero-illo-commodi-velit** can encode and decode: **strings**, **files** and **strings with XOR encrytion**.

[![nodei.co](https://nodei.co/npm/@devtea2028/libero-illo-commodi-velit.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/@devtea2028/libero-illo-commodi-velit/)

## Why use this module?
It's minimalist and focused in the best javascript performance.


### Install @devtea2028/libero-illo-commodi-velit module
At cmd, type:
```
$ npm install @devtea2028/libero-illo-commodi-velit
```
or to install this package globally, use:

```
$ npm install -g @devtea2028/libero-illo-commodi-velit
```

### After install run unit tests

```
$ cd ./node_modules/@devtea2028/libero-illo-commodi-velit/
$ npm install
$ npm test
```
<img src="http://i.imgur.com/U7rayiT.png"/>

### Do you want a test report?

```
$ cd ./node_modules/@devtea2028/libero-illo-commodi-velit/
$ npm install
$ npm test  --coverage
```
<img src="http://i.imgur.com/sIZfdP8.png"/>

## How to use?
To load module functionalities, you must use the require.js properties integrated in node.js.

Example:
```javascript
var base64 = require('@devtea2028/libero-illo-commodi-velit');
```
### DOCS

##### encode (str)
This method is used to encode a plain-text string to a encoded string in base64.
- **Arguments :**
- ```str``` - The string you want to encode.
- ```type``` - Encoding Type (This argument is optional) | Available types: 'MIME'.
- **Result :**  Encoded string in base64.
- **Example :**
```javascript
base64.encode('@devtea2028/libero-illo-commodi-velit npm module'); // result = YmFzZTY0LW1pbiBucG0gbW9kdWxl
base64.encode('@devtea2028/libero-illo-commodi-velit npm module', 'MIME'); // result = YmFzZTY0LW1pbiBucG0gbW9kdWxl
                                                 // encoded string in base64, using MIME constraints
```
##### decode (str)
This method is used to decode a the base64 message to a plain-text string.
- **Arguments :**
- ```str``` - The message (in base64) you want to decode.
- **Result :**  Our message decoded in plain-text.
- **Example :**
```javascript
base64.decode('YmFzZTY0LW1pbiBucG0gbW9kdWxl'); // result = @devtea2028/libero-illo-commodi-velit npm module
```
##### encodeFile(file)
This method is used to encode files into base64 string.
- **Arguments :**
- ```file``` - The file path of the you want to encode.
- **Result :**  Encoded File into a string in base64.
- **Example :**
```javascript
base64.encodeFile('original.png');
```
##### decodeToFile(str,filepath)
This method is used to decode messages and save the result in one file (Tested and functional with PNG Files).
- **Arguments :**
- ```str``` - The message (in base64) you want to decode.
- ```file``` - The file path of the you want to save.
- **Result :**  Decoded File
- **Example :**
```javascript
base64.decodeToFile('ZGF0YQ==', 'result.png') ;
```
##### encodeWithKey(str,key)
This method is used to encode messages and encrypt messages using a key (XOR Encryption - Fast and "Secure").
- **Arguments :**
- ```str``` - The message in plain-text.
- ```key``` - The key you want to encrypt your message.
- **Result :**  Encoded encrypted message in base64.
- **Example :**
```javascript
base64.encodeWithKey('@devtea2028/libero-illo-commodi-velit npm module', 'victorfern91'); // result = FAgQEVlGSwgbABlfBgRDGQAWEwkX
                                                               //(in plain text is YFK_C	)
```
##### decodeWithKey(str,key)
- **Arguments :**
- ```str``` - The message in base64.
- ```key``` - The key used to encrypt this message.
- **Result :**  Deciphered message in plain-text.
- **Example :**
```javascript
//Decoding with wrong key
base64.decodeWithKey('FAgQEVlGSwgbABlfBgRDGQAWEwkX', 'npm module'); // result = zx}14)/}wew/k$.vdcly
//Decoding with correct key
base64.decodeWithKey('FAgQEVlGSwgbABlfBgRDGQAWEwkX', 'victorfern91'); // result = @devtea2028/libero-illo-commodi-velit npm module
```
