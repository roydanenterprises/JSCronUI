# JSCronUI
A jQuery extension for generating [Quartz](http://quartz-scheduler.org/documentation/quartz-2.x/tutorials/crontrigger) cron expressions.

## About
JSCronUI offers a comprehensive interface for users to schedule tasks, while allowing developers to leverage the power of cron. Additionally, JSCronUI provides a cron-to-english converter, allowing the ability for users to see a brief summary of the schedule without having to open the full UI.

Developers can provide a customized template to run JSCronUI on top of, or use the included template.

## How To Use
You can create a `new jsCronUI(settings, element)` in-memory and call the methods directly.
JSCronUI also extends jQuery, and a new instance can be created by calling `.jsCronUI()` on any jQuery object. Once created, call any of the methods by calling `.jsCronUI('methodName', arguments)` on the same jQuery object. 

In both cases, JSCronUI will automatically inject the necessary DOM to the given element. 

## Settings
When creating a new instance of JSCronUI, you can provide a `settings` object to the constructor to change some of the default settings. All properties are optional.
* `bindTo` - A jQuery object to be updated with the current cron string whenever a change is made.
* `container` - A jQuery object representing the [UI template](#templates) to use. If this property is not specified, the default template is used.
* `initialValue` - The starting value JSCronUI should hold after construction is complete.

## Available Commands
* `reset()` - Reverts JSCronUI to the default state (`0 * * * * ? *`).
* `setCron(expression)` - Sets JSCronUI to reflect the given cron string.
* `getCron(validate)` - Returns a cron string representing the current state of JSCronUI. 
	* If `validate` is truthy, this method will throw exceptions if any options required to generate the cron string are missing. 
	* If `validate` is falsey, any missing options will be interpreted as `*` or `?` (as necessary) within the cron string.
* `toEnglishString()` - Returns an English string describing the current state of JSCronUI. 

## Templates
JSCronUI uses a DOM template to handle UI interactions. If you do not specify a template, a default UI template will be used instead. To use a custom template, provide a jQuery object of the template as the `container` property of the `settings` object when creating the JSCronUI instance. For example:

```html
<div class="js-cron">
    <div class="js-cron-template">
        .
        .
        .
    </div>
<div>
```

```javascript
var cron = $('.js-cron');
var template = $('.js-cron .js-cron-template');
var settings = {
    container: template
};
cron.jsCronUI(settings);
```

Will create a new JSCronUI instance on the `js-cron` `div`, using the nested `js-cron-template` `div` as the UI interface. 

This can be helpful if you need extra information or custom markup within the template, but don't want to interfere with the UI implementation.