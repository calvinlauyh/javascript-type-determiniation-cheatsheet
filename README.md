## Behaviours of JavaScript `Object.prototype.toString()` and `typeof` in different browsers

### Background
`typeof` and `Object.prototype.toString()` are two common tools used for determining a variable type. This document summarizes the behaviours of these two functions when given different variable types in different browsers.

### `Object.prototype.toString()`
| argument | IE8 | IE9 | IE10 | IE11 | Edge | Firefox | Chrome | Safari |
| -------- | --- | --- | ---- | ---- | ---- | ------- | ------ | ------ |
| null |**_[object Object]_** | [object Null] | [object Null] | [object Null] | [object Null] | [object Null] | [object Null] | [object Null] | 
| undefined | **_[object Object]_** | [object Undefined] | [object Undefined] | [object Undefined] | [object Undefined] | [object Undefined] | [object Undefined] | [object Undefined] | 
| [] | [object Array] | [object Array] | [object Array] | [object Array] | [object Array] | [object Array] | [object Array] | [object Array] | 
| new Array() | [object Array] | [object Array] | [object Array] | [object Array] | [object Array] | [object Array] | [object Array] | [object Array] | 
| {} | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | 
| new Object() | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | 
| "Hello World" | [object String] | [object String] | [object String] | [object String] | [object String] | [object String] | [object String] | [object String] | 
| 1 | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | 
| 1.1 | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | 
| NaN | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | [object Number] | 
| true | [object Boolean] | [object Boolean] | [object Boolean] | [object Boolean] | [object Boolean] | [object Boolean] | [object Boolean] | [object Boolean] | 
| function(){} | [object Function] | [object Function] | [object Function] | [object Function] | [object Function] | [object Function] | [object Function] | [object Function] | 
| /[a-z]/ | [object RegExp] | [object RegExp] | [object RegExp] | [object RegExp] | [object RegExp] | [object RegExp] | [object RegExp] | [object RegExp] | 
| new Date() | [object Date] | [object Date] | [object Date] | [object Date] | [object Date] | [object Date] | [object Date] | [object Date] | 
| document.getElementById('result') | **_[object Object]_** | [object HTMLDivElement] | [object HTMLDivElement] | [object HTMLDivElement] | [object HTMLDivElement] | [object HTMLDivElement] | [object HTMLDivElement] | [object HTMLDivElement] | 
| document.getElementsByTagName('div') | **_[object Object]_** | [object HTMLCollection] | [object HTMLCollection] | [object HTMLCollection] | [object HTMLCollection] | [object HTMLCollection] | [object HTMLCollection] | [object NodeList] | 
| arguments | [object Object] | [object Arguments] | [object Arguments] | [object Arguments] | [object Arguments] | [object Arguments] | [object Arguments] | [object Arguments] | 
| new Test() | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | 
| new Test() | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] | [object Object] |  [object Object] |

### `typeof`
| argument | IE8 | IE9 | IE10 | IE11 | Edge | Firefox | Chrome | Safari |
| -------- | --- | --- | ---- | ---- | ---- | ------- | ------ | ------ |
| null | object | object | object | object | object | object | object |object |
| undefined | undefined | undefined | undefined | undefined | undefined | undefined | undefined |undefined |
| [] | object | object | object | object | object | object | object |object |
| new Array() | object | object | object | object | object | object | object |object |
| {} | object | object | object | object | object | object | object |object |
| new Object() | object | object | object | object | object | object | object |object |
| "Hello World" | string | string | string | string | string | string | string |string |
| 1 | number | number | number | number | number | number | number |number |
| 1.1 | number | number | number | number | number | number | number |number |
| NaN | number | number | number | number | number | number | number |number |
| true | boolean | boolean | boolean | boolean | boolean | boolean | boolean |boolean |
| function(){} | function | function | function | function | function | function | function |function |
| /[a-z]/ | object | object | object | object | object | object | object |object |
| new Date() | object | object | object | object | object | object | object |object |
| document.getElementById('result') | object | object | object | object | object | object | object |object |
| document.getElementsByTagName('div') | object | object | object | object | object | object | object |object |
| arguments | object | object | object | object | object | object | object |object |
| new Test() | object | object | object | object | object | object | object |object |
| new Test() | object | object | object | object | object | object | object | object |

Remarks:
- IE8: Tested on Internet Explorer Version 8.0.7601.17514 running on Windows 7
- IE9: Tested on Internet Explorer Version 9.0.8112.16421 running on Windows 7
- IE10: Tested on Internet Explorer Version 10.0.9200.17148 running on Windows 7
- IE11: Tested on Internet Explorer Version 11.321.14393.0 running on Windows 7
- Edge: Tested on Microsoft Edge 38.14393.0.0 running on Windows 7
- Chrome: Tested on Chrome Version 53.0.2785.143 m (64-bit) running on Windows 7
- Firefox: Tested on Firefox Version 48.0.2 running on Windows 7
- Safari: Tested on Safari Version 10.0 (11602.1.50.0.10) running on Mac OS X El Capitan
