# Change Log

All notable changes to this project will be documented in this file.

## [Unreleased]

## [1.1.0] - 2016-07-05
- Remove non-decimal characters from date input fields
- Truncate decimal values in date input fields to just the integer component
- Remove duplicate date values from date input fields (eg, '2,2,2,2' will result in '2')
- Disable input fields that are not related to the sub-type selection for Monthly and Yearly options
- When validating, throw an error when any of the provided days are larger than 31

## [1.0.0] - 2016-06-03
- Extracted default template to seperate file to make editing easier.
- Flattened the internal model to make it easier to work with
- Updated error handling to be based on a list of messages, rather than hard-coded when creating the error
- Made it easier to construct an instance of JSCronUI

## 0.0.1 - 2016-06-03
- Initial Release



[Unreleased]: https://github.com/roydanenterprises/JSCronUI/compare/v1.1.0...HEAD
[1.1.0]: https://github.com/roydanenterprises/JSCronUI/compare/v0.0.1...v1.1.0
[1.0.0]: https://github.com/roydanenterprises/JSCronUI/compare/v0.0.1...v1.0.0