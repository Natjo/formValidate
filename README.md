
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
### No Ajax
Check validity of form before submit.
```javascript
import formValidate from '../../modules/formValidate/formValidate.js';

const form = document.querySelector('form');
formValidate(form, () => {
    form.submit();
});
```
### Ajax
Check validity of form before submit.
```javascript
import formValidate from '../../modules/formValidate/formValidate.js';

const form = document.querySelector('form');
const url = paramsData.wp_ajax_url;
formValidate(form, () => {
    const formData = new FormData(form);
    formData.append('nonce', form.dataset.nonce);
    formData.append('action', form.action);

    const xhr = new XMLHttpRequest();
    xhr.open('POST', url, true);
    xhr.onreadystatechange = () => {
        if (xhr.readyState === 4 && (xhr.status === 200 || xhr.status === 0)) {
            // const response = JSON.parse(xhr.response);
            form.reset();
            modal.open();
        }
    };
    xhr.send(formData);
});
```

## Demo
[See codepen demo](https://codepen.io/natjo/pen/NmMzNd?editors=0011)


