
# Form validate

![version](https://img.shields.io/github/manifest-json/v/Natjo/formValidate)  

  

Validation js native and accessible.  
See [Form](https://github.com/Natjo/form) for markup and css

## Parameters
| Parameter | Type | Default | Description |
| ------ | ------ | ------ | ------ |
| form | HTMLElement | - | form element |


## Methods & Properties
| Methods | Description |
| ------ | ------ |
| formValidate.reset() | -- |

## Events
| Name | Arguments | Description |
| ------ | ------ | ------ |
| onSend | - | fire if form valid |


## Usage
```javascript
import formValidate from '../../modules/formValidate/formValidate.js';

const form = document.querySelector('form');
formValidate(form, () => {
    console.log('send');
});

```

## Demo
[See codepen demo](https://codepen.io/natjo/pen/NmMzNd?editors=0011)


