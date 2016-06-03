# JSCronUI
A jQuery extension for generating [Quartz](http://quartz-scheduler.org/documentation/quartz-2.x/tutorials/crontrigger) cron expressions.

## About
JSCronUI offers a comprehensive interface for users to schedule tasks, while allowing developers to leverage the power of cron. Additionally, JSCronUI provides a cron-to-english converter, allowing the ability for users to see a brief summary of the schedule without having to open the full UI.

Developers can provide a customized template to run JSCronUI on top of, or use the included template. If an empty template is provided, JSCronUI can also be used without a UI to validate cron strings or quickly convert a cron string to english.

## How To Use
You can create a `new jsCronUI(settings, element)` in-memory and call the methods directly.
JSCronUI also extends jQuery, and a new instance can be created by calling `.jsCronUI()` on any jQuery object. Once created, call any of the methods by calling `.jsCronUI('methodName', arguments)` on the same jQuery object. 

In both cases, JSCronUI will automatically inject the necessary DOM to the given element. 


## Available Commands
* `reset()` - Reverts JSCronUI to the default state (`0 * * * * ? *`).
* `setCron(expression)` - Sets JSCronUI to reflect the given cron string.
* `getCron(validate)` - Returns a cron string representing the current state of JSCronUI. 
	* If `validate` is truthy, this method will throw exceptions if any options required to generate the cron string are missing. 
	* If `validate` is falsey, any missing options will be interpreted as '*' within the cron string.
* `toEnglishString()` - Returns an English string describing the current state of JSCronUI. 