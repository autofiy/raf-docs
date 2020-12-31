---
id : field

title : Field
---

in this page we will talk about the configuration of the field.

there are many options for configuring the field but only two are required

* **name**  : string
* **as**    : the component that represent the field, raf-core bring with it default fields that you can use such
  as `DefaultTextField`,`DefaultPasswordField`, ...

let's take configuration options by category

#### UI

    {
        readonly: boolean;              
        message: string;               
        messageType: FieldMessageType;  
        disableOnLoading: boolean;     
        disableOnFormLoading: boolean; 
        hidden: boolean;               
        disabled: boolean;             
        loading: boolean;              
    }

* **readonly** indicate weather the field is readonly or not (true for readonly)
    - default : false


* **message** label message attached to field to display some information such as error message
    * default : `""`


* **messageType** the type of the message
    - default : `FieldMessageType.INFO`


* **disableOnLoading** indicate to disable the field when the field start loading (true for disabling)
    - default : false


* **disableOnFormLoading** indicate to disable the field when the form start loading (true for disabling)
    - default : true


* **hidden** indicate should the field be hidden (true to hide)
    - default : false


* **disabled** indicate disable state for the field (true to disable)
    - default : false


* **loading** indicate loading state for the field
    - default : false

#### Collecting

    {
        ready: boolean;                   
        skipCollecting: boolean;          
        asQuery: boolean;                 
        collect: (field: IField) => any;   
    }

* **ready** : indicate weather the field ready to be collected
    - default : false


* **skipCollecting** : set to `true` to skip collecting the field when the form collect data
    - default : false


* **asQuery** : set to `true` to submit the value of the field as query parameter
    - default : false


* **collect** : callback function to return the collected value
    - default : return the value of the field without any modification

#### Validation

    {
        validateOnChange: boolean;
        rules: any;
        skipValidation: boolean;
        valid: boolean;
        validator: ((field: IField) => Validator) | null;
        updateMessageOnValidationFail: boolean,
        onFailMessageType: FieldMessageType;
    }

* **validationOnChange** indicate to validate the field when value changed
    - default : true


* **rules** validation rules
    - default : `{}`


* **skipValidation** set `true` to make the form skip validating the field
    - default : false


* **valid** : valid state for the field
    - default : tru

* **validator** : provide custom validator for the field so that it will be used instead of the default form validator
    - default : `null`


* **updateMessageOnValidationFail** : indicate to update the `message` option for the field when validation fails, the
  message will be set from the result of the validator
    - default : false

* **onFailMessageType** : the type of the message when validation fails and message set from the validation result
    - default `FieldMessageType.ERROR`

#### Value

    {
        value: any;
        clearValue: any;
        defaultChangeHandler: (field: IField) => FieldChangeHandler;
        extractValueFromEvent?: (event: any) => any;
    }

* **value** : the value of the field
    - default : `""`


* **clearValue** : the value that will be set to the field when `.clear()` called
    - default : `""`


* **defaultChangeHandler** : a custom value change handler for the field
    - default : a new instance of `DefaulFieldChangeHandler` class


* **extractValueFromEvent** : value extractor callback from passed input event
    - default : `undefined`
    - the default will be changed on next version
    - the field will check if the extractor is passed and use it if so, if not the field will use this
      `e => e.target.value` as extractor

#### Event

    {
        listenThis?: { [eventName: string]: EventCallback; };
    }

* **listenThis** : object of listeners that will be called when event on the field triggered
    - default : `undefined`
    - the name of the option will be changed on the next version
    - available events that could be listened to are : `FieldEvents.VALIDATION_FAIL` and `FieldEvents.CHANGE`

#### Extra

    {
        extra : any
    }

the `extra` option is used by the modules that will extend the behavior of the field, it can hold any type of data.

you will see the usage of the extra in advance section and in other sibling packages.

### Will You Need All These Options

you may say these are too many options, and you're correct again!, you will not need to set many of these options, all
of them are set to default values that fit the most use cases, but they are their if you need to. actually many of them
if you need to change, you will change from event listener of some other callback functions, later we will see how to
change the options.



### Options Summary


    {

        name : string;
        as : typeof Field;


        readonly: boolean;              
        message: string;               
        messageType: FieldMessageType;  
        disableOnLoading: boolean;     
        disableOnFormLoading: boolean;
        hidden: boolean;               
        disabled: boolean;             
        loading: boolean;         


        ready: boolean;                   
        skipCollecting: boolean;          
        asQuery: boolean;                 
        collect: (field: IField) => any;


        validateOnChange: boolean;
        rules: any;
        skipValidation: boolean;
        valid: boolean;
        validator: ((field: IField) => Validator) | null;
        updateMessageOnValidationFail: boolean,
        onFailMessageType: FieldMessageType;


        value: any;
        clearValue: any;
        defaultChangeHandler: (field: IField) => FieldChangeHandler;
        extractValueFromEvent?: (event: any) => any;


        listenThis?: { [eventName: string]: EventCallback; };


        extra : any
    }