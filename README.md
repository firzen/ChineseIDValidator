#IDValidator.js

Chinese Personal ID Card Validation for Javascript

Support length 15 and 18.

##API
`isValid()` Boolean Result of validation

`getInfo()` Return details of the ID(area/birthday/sex/validcode), false if invalidate.

`makeID()` Make a sample ID


##Getting Start

###Flat
```html
<script type="text/javascript" src="path/to/IDValidator/IDValidator.min.js" charset="utf-8" ></script>
<script type="text/javascript" src="path/to/IDValidator/GB2260.min.js" charset="utf-8" ></script>
<script type="text/javascript">

    //New Instance
    var Validator = new IDValidator();

    //New Instance with area check
    var Validator = new IDValidator( GB2260 );

</script>
```

###CommonJS / Node
```javascript
var IDValidator = require('path/to/IDValidator');
var GB2260 = require('path/to/GB2260');

var Validator = new IDValidator();

//with area check
var Validator2 = new IDValidator( GB2260 );

```
Tips: GB2260.js is optional.

Compressed:

IDValidator.min.js 3K 

GB2260.min.js 140K 

##Sample:

Instance:
```js
var Validator = new IDValidator();
```
With GB2260
```js
var Validator = new IDValidator( GB2260 );
```

Validation
```js
//Please use string format
var id = "123456789012345678";

Validator.isValid( id );
//true if verify.
```
Tips:

1. Please use string format of ID


Get ID info
```js
Validator.getInfo( id );
/* 
 * Verified:
 * {
 *   'addrCode': 100101, //Area code,
 *   'addr':     '北京市东城区', //area, with  GB2260
 *   'birth':    '1988-01-20', //birthday
 *   'sex':      1, //sex，0 for female，1 for male
 *   'checkBit': 'X', //validate code，for length 18 ID
 *   'length':   18 //ID type 15 or 18
 * }
 */
```

Make an ID
```js
//make an 18 ID
var ID = Validator.makeID();

//make an 15 ID
var ID = Validator.makeID( true );
```
More [`examples`](https://github.com/mc-zone/IDValidator/tree/master/examples/) .

##Links
GB 11643-1999 公民身份证号码

GB 2260-1995 中华人民共和国行政区划代码

## License
MIT


