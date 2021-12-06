
# Form validate

![version](https://img.shields.io/github/manifest-json/v/Natjo/formValidate)  

  
Validation js native
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
new formValidate(form, () => {
    form.submit();
});
```
### Ajax
Send **ajax** if form is valid.  
If **nonce** needed, add it to the form with `data-nonce`  

| Error | Description |
| ------ | ------ |
| `300` | error validation field |
| `200` | ok |
| `500` | error sending email |

```javascript
import formValidate from '../../modules/formValidate/formValidate.js';

const form = document.querySelector('form');
const url = paramsData.wp_ajax_url;
new formValidate(form, e => {
    const formData = new FormData(form);
    formData.append('nonce', form.dataset.nonce);
    formData.append('action', form.getAttribute('action'));

    const xhr = new XMLHttpRequest();
    xhr.open('POST', url, true);
    xhr.onload = () => {
        const response = JSON.parse(xhr.response);
        if(response.status === 200){
            form.reset();
            e.reset();
        }
        if(response.status === 300){
            console.log(response.msg);
        }
        if(response.status === 500){
            console.log(response.msg);
        }
    }
    xhr.error = () => {
       console.log('error');
    }

  // Définissez ce qui arrive en cas d'erreur
  xhr.addEventListener('error', function(event) {
    alert('Oups! Quelque chose s\'est mal passé.');
  });
    xhr.send(formData);
});
```
Add action in *ajax-method.php*, and return json with `status` and `msg`.  

```php
add_action( 'wp_ajax_mmyAction', 'mmyAction_callback' );
add_action( 'wp_ajax_nopriv_mmyAction', 'mmyAction_callback' );

function myAction_callback()
{
    $response['status'] = 200;
    $response['msg'] = __('Your message has been send', 'lsd_lang');

    wp_send_json($response);
}
```
## Demo
[See codepen demo](https://codepen.io/natjo/pen/NmMzNd?editors=0011)


