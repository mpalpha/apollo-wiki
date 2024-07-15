[Research Spike]( https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_workitems/edit/572): Research Spike: Does the Date input have validation attribute with ValidityState constraint validation?

### Notes
The displayed date format will differ from the actual value — the displayed date is formatted based on the locale of the user's browser, but the parsed value is always formatted yyyy-mm-dd. 

By default, `<input type="date">` doesn't validate the entered value beyond its format. 
The interfaces in modern browsers generally don't let you enter anything that isn't a date.  Some will prevent entering dates outside of a min/max range if set. See next

### Validation Properties

The following properties are available on the ValidationState object of the date input.

| ValidationState Property| HTML Attribute |
|--|--|
| valueMissing | required |
| typeMismatch | n/a |
| patternMismatch |	n/a |
| tooLong |	n/a |
| tooShort |	n/a |
| rangeUnderflow | Min |
| rangeOverflow | Max |
| stepMismatch | Step |
| badInput | n/a |
| customError |	n/a |
| valid | n/a |

### Browser behavior 

Tested in 
Firefox 96 
Chrome 96
Edge 96
Safari 14.1

The table below shows the UI behavior when testing properties that are used on a date input.

![Screen Shot 2022-01-12 at 3.14.27 PM.png](/.attachments/Screen%20Shot%202022-01-12%20at%203.14.27%20PM-0dbeb378-4213-40b6-be1c-ca2199adaf03.png)

See testing codepen [here](https://codepen.io/tx-tim-the-selector/pen/KKXrKyq)

### Recommendation

We should try and make the native date input functionality work since we get formatting based on the locale of the user's browser for free.

Validation methods can pay attention to valueMissing, rangeUnderflow, rangeOverflow, and stepMismatch.

Use `min` and `max` properties to set sensible defaults.  Information on credit card expiration dates is inconsistent but suggests between [3](https://www.cardrates.com/advice/when-do-credit-cards-expire/) and [20](https://stackoverflow.com/a/60567427/981556) [years](https://joshuatauberer.medium.com/designing-a-credit-card-expiration-date-drop-down-how-many-years-in-the-future-to-list-7b171f555706).
