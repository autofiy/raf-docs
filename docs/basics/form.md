---
id : form

title : Form Configuration
---


in this page we will talk about form configuration.


only the `fields` option is required, other configuration options are optional.


the options are : 

    {
        fields: (FieldOptions | FieldOptions[])[],
    
        listen?: {
            [eventName: string]: EventCallback;
        },
    
        onAnyValueChanged?: (key: string, value: any, field: IField, form: IForm) => void,
        initialValues?: any,
        allowSubmitWhenNotValid?: boolean;
        extra?: any;
    }


* **fields** array of field options where you describe the fields of the form



* **listen** listener object where you can define a listener on any event, see `GlobalEvents` to see what
    events that you can listen to



* **onAnyValueChange** call back function that will be called when any value of any field changed



* **initialValues** set initial values for the form when it first rendered


* **allowSubmitWhenNotValid** set `true` if you want the submitting triggered when the user clicks the submit button even if the form is not valid


* **extra** object to define extra configuration that can be used by the form services


* **services** : where you define you custom services like form rendering and submitting, ...



