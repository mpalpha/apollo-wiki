The input validation library can be found in `packages/components/src/utils/validator.ts`. 

Implementation for the input validation library was based on this [blog post](https://medium.com/@sebastien.lubineau/input-validation-with-stenciljs-f464644545c8).  The general concept is to provide the ability to validate user input inline (without having to wait for form submission) through a separate module that can be reused across components.  

The library makes use of the [`validity` property](https://developer.mozilla.org/en-US/docs/Web/API/HTMLObjectElement/validity) in the browsers' constraint validation API.
The `validity` property returns a [validity state]  [Validity State](https://developer.mozilla.org/en-US/docs/Web/API/ValidityState) object which reports on the validity of an input's value relative to the validation constraints on the element.

Summary of ValidityState interface


| validity property | html attribute| description |
|--|--|--|
| valueMissing |required |  A boolean value that is true if the element has a required attribute, but no value, or false otherwise. |
| patternMismatch | pattern | A boolean value that is true if the value does not match the specified pattern, and false if it does match. |
|rangeOverflow | max |  A boolean value that is true if the value is greater than the maximum specified by the max attribute, or false if it is less than or equal to the maximum. |
| rangeUnderflow | min |  A boolean value that is true if the value is less than the minimum specified by the min attribute, or false if it is greater than or equal to the minimum. |
| stepMismatch | step |  A boolean value that is true if the value does not fit the rules determined by the step attribute (that is, it's not evenly divisible by the step value), or false if it does fit the step rule. |
| tooLong | maxlength | A boolean value that is true if the value exceeds the specified maxlength for HTMLInputElement or HTMLTextAreaElement objects, or false if its length is less than or equal to the maximum length. Note: This property is never true **in Gecko**, because elements' values are prevented from being longer than maxlength. |
| tooShort | minlength | A boolean value that is true if the value fails to meet the specified minlength for HTMLInputElement or HTMLTextAreaElement objects, or false if its length is greater than or equal to the minimum length. |
| typeMismatch | n/a | A boolean value that is true if the value is not in the required syntax (when type is email or url), or false if the syntax is correct. |
| valid | n/a | A boolean value that is true if the element meets all its validation constraints, and is therefore considered to be valid, or false if it fails any constraint. |
| badInput | n/a | A boolean value that is true if the user has provided input that the browser is unable to convert. |
| customError | n/a | A boolean value indicating whether the element's custom validity message has been set to a non-empty string by calling the element's setCustomValidity() method. |

## Caveats
Native elements will match the :invalid CSS pseudo-classe (and possibly others e.g. :out-of-range) if the input validity fails. Custom elements cannot use the `:invalid` selector in CSS for custom elements but there is a [proposed addition to the web components spec](https://github.com/WICG/webcomponents/issues/300) that would allow for the addition of custom pseudo-elements.

As of this writing (4.25.2022) the following features are implemented or planned:

- valueMissing
- patternMismatch
- tooLong
- tooShort
- rangeOverflow
- rangeUnderflow

**Usage**

Initialize the validator in the `componentWillLoad` lifecycle event

```
    this.validator = initializeValidators(this);
```

this.validator implements the Validator interface

```
{
  errorMessage?: string;
  validate: (htmlInput) => boolean;
}
```

Run the `validate` function to determine the validity of the input's value.

`false` - The validation failed; `errorMessage` property will contain the error message assigned to that particular validation

`true` - The validation passed; the `errorMessage` will be an empty string `''`

**Examples:**  
Trivial example of conditionally rendering the `errorMessage` based on the return value of the `validator` function:

```
!this.validator.validate(this.hiddenInput) && 
    <p>{this.validator.errorMessage}</p>
}
```

Realistic example of conditionally rendering the `errorMessage` based on the return value of the `validator` function:

```
render() {
...
{(!this.isInitialRender || this.error) && !this.validator.validate(this.hiddenInput) && (
    <abds-supporting-text errorText={this.validator.errorMessage}></abds-supporting-text>
)}
```

