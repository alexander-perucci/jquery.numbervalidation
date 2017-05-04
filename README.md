jQuery Number Validation Plugin
=======================

Number Validation Plugin is a plugin for jQuery that performs validation of an HTML input number type.

## Getting Started

### Downloading Number Validation Plugin

Number Validation Plugin can be downloaded [here](https://github.com/prednaxela/jquery.numbervalidation/archive/master.zip)

### Dependencies

Number Validation Plugin use:

 1. Bootstrap Tooltips [download](http://getbootstrap.com/)
 2. jQuery [download](http://jquery.com/) 
 
### Including it on your page

Include Bootstrap, jQuery and the Number Validation Plugin on a page.

```html
<script type='text/javascript' src='jquery.js'></script>
<script type='text/javascript' src='bootstrap.js'></script>
<script type='text/javascript' src='jquery.numbervalidation.js'></script>
```
### Number Validation Plugin functions
| Name          | Parameters      |Return            | Description  |
| ------------- |:---------------:|:----------------:|:------------|
| masknumber    | Yes             | none             | Apply the plugin |
| validnumber   | Yes             | `true` or `false`| Check if input is valid|

### Structure of parameters
<pre>
  {
    rules:{
      type,
      required,
      maxvalue,
      minvalue,
      decimals,
      length
    },  
    messages:{
      type,
      required,
      maxvalue,
      minvalue,
      decimals,
      length
    },
    settingserror:{
      setting,
      tooltipplacement,
      tooltiptrigger,
      bordercolorok,
      bordercolornotok
    }
  }
</pre>

#### Setting `rules` parameter

| Name          | Value           |Default      | Description  |
| ------------- |:---------------------:|:-------------:|:------------|
| `type`          | 'integer' or 'double' | 'integer'     | Define a type of Html input|
| `required`      | `true` or `false`         | `false`         | Check if input has a value if required is `true`|
| `maxvalue`      | number                | undefined     | Check if input has a value greater than `maxvalue` |
| `minvalue`      | number                | undefined     | Check if input has a value less than `minvalue`  |
| `length`        | number                | undefined     | Check if the number of characters that makes up the integer part of the input value is greater than `length` |
| `decimals`      | number                | undefined     | Check if the number of characters that makes up the decimal part of the input value is greater than `decimals` |

#### Setting `messages` parameter
| Name          | Value  |Default | Description  |
| ------------- |:------:|:------:|:------------|
| `type`        | string | " "     | Define a error message for the rule `type`|
| `required`    | string | " "     | Define a error message for the rule  `required`|
| `maxvalue`    | string | " "     | Define a error message for the rule  `maxvalue` |
| `minvalue`    | string | " "     | Define a error message for the rule  `minvalue`|
| `length`      | string | " "     | Define a error message for the rule  `length`|
| `decimals`    | number | " "     | Define a error message for the rule  `decimals`|

#### Setting `settingserror` parameter
| Name               | Value  |Default | Description  |
| ------------------ |:------:|:------:|:------------|
| `setting`    |`true` or `false`         | `true`     |If the property is set a `false`, the error message is not shown   |
| `tooltipplacement` | 'top', 'bottom', 'left', 'right' or 'auto' | 'bottom' | How to position the tooltip. When 'auto' is specified, it will dynamically reorient the tooltip. For example, if placement is "auto left", the tooltip will display to the left when possible, otherwise it will display right|
| `tooltiptrigger`   | 'click', 'hover', 'focus' or 'manual' | 'hover'     | How tooltip is triggered. You may pass multiple triggers; separate them with a space|
| `bordercolorok`    | string | Current color of the input     | Define a `border-color` property of the input when the validation return true |
| `bordercolornotok` | string | 'red'     | Define a `border-color` property of the input when the validation return false |

### Example double type
```html
<input type="text" id="double" name="double">
```

```javascript
$("#double").masknumber({
    rules: {
        type: 'double',
        decimals: 2,
        maxvalue: 100,
        minvalue: 3
    },
    messages: {
        type: "The value is not decimals",
        decimals: "The max number of decimals is 2",
        maxvalue: "The value is greater than 100",
        minvalue: "The value is less than 3"
    },
    settingserror: {
        tooltipplacement: "right"
    }
});
```
### Example validation function

```html
<input type="text" id="double" name="double">
```

```javascript
$("#double").validnumber({
    rules: {
        type: 'double',
        decimals: 2,
        maxvalue: 100,
        minvalue: 3
    },
    settingserror: {
        setting: false
    }
});
```
This `validnumber` function return `true` or `false` if and only if the value of the input is valid for the `rules` setted. Since that the parameter `setting` is setted a `false`, the error message is not shown in the Html input.

## Reporting an Issue

1. Make sure the problem you're addressing is reproducible.
2. Use http://jsbin.com or http://jsfiddle.net to provide a test page.
3. Indicate what browsers the issue can be reproduced in. **Note: IE Compatibilty modes issues will not be addressed.**
4. What version of the plug-in is the issue reproducible in. Is it reproducible after updating to the latest version.

## Contribute
You can also support this project by donating on Gratipay [here](https://www.gratipay.com/alexander_perucci/)

## License
Licensed under the MPL version 2.0 license.

Copyright (c) 2014 Alexander Perucci.
