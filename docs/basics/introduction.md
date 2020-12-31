---
id: introduction

title: Introduction
---


For me it was always frustrating when it comes to forms, I will need to design the UI and then write the validation
logic and then I need to handle submitting the data. the frustration grow as the form grow. this process could take
decent time.

the time will increase as the form keep growing.

**Raf-Core** to rescue by addressing these tasks and more in very customizable manner, Raf-Core is library belong
to [Autofiy](https://www.github.com/autofiy) project.

this library handle :

* UI (Rendering)
* Validation
* Submitting
* Collecting
* Events
* And More

in very few minutes you can write large form with many functionalities by just writing simple configurations

:::note

Raf stands for React Auto Form

:::

### Installation

using **npm**

    npm install @autofiy/raf-core

using **yarn**

    yarn add @autofiy/raf-core

### Example

    import {Form , DefaultTextField , DefaultPasswordField }  from "@autofiy/raf-core";
    
    export class Demo extends Component {
        render() {
            return <Form fields={[
                    {as: DefaultTextField, name: 'username', extra: {label: 'Username'}},
                    {as: DefaultPasswordField, name: 'password', extra: {label: 'Password'}},
                    {as: DefaultCheckboxField, name: 'rememberMe', extra: {label: 'Remember'}},
                ]} extra={{
                    submitOptions: {
                        url: '...'
                    },renderOptions: {
                        buttonText: 'Login',
                    },
                }} />;
        }
    }

[See&Edit On Sandbox](https://codesandbox.io/s/lingering-fast-14bp5?file=/src/App.js)

you may say this form is ugly, and yes it's ugly but keep in mind this library is the core and because it's
customizable, there are many sibling packages improve what you need like rendering you will see the current available
options later.

