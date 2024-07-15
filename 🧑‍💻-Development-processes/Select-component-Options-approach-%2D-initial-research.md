Users need to be able to add options to `<abds-select>` component. This document summarizes research into two approaches to the problem - by having users pass an array of objects as a prop directly to `<abds-select>`, or, having users nest `<option>` to be slotted within `<abds-select>` .

For better user experience, as much as possible should be handled by our component vs by the implementors. Also for better user experience, the slotted approach (Approach 2) would be preferable, as it most closely mimics native functionality and works best with dev tools - a POC is needed to check the viability of this approach.

## Approach 1 - Users pass an array of objects as a prop

#### Implementation Example: 
```
<abds-select options='[{'name': 'alpha',
  'value': 'one'
  },
  {"name": "beta",
  "value": "two"
  },
  {"name": "gamma",
  "value": "three"
  }]'></abds-select>
```

#### Problem:

Given a `SelectOption` object with `name` and `value` attributes:
```
SelectOption { 
     name: string 
     value: string 
 
}
```
 
When an Array of `SelectOptions` is provided to a custom element's options property,

How do we render that Array of `SelectOptions` as a list of `option` tags with the name as the text content and the value as the `value` attribute?

e.g.
`<option value={value}>{name}</option>`

#### Solution: 

Use JSON.parse to convert the passed string containing the array of options into an array, then loop through that array to create `option` element for each item, which is then appended to our host element.

### Pros
- Self-contained - no need for a custom option component
- In theory, the options will be associated with our select out the box
- Fast to create options
- Adding options in React is simple, just pass a variable as the prop

### Cons
- It looks ugly & doesn’t work well with formatting tools (indentation), linting doesn’t detect issues
- HTML requires the array be a string and JSON.parse is strict (requires only double quotes within the string, no trailing commas)
- Error prone due to above, a little opaque
- React wants a unique key attribute for each option, which wouldn’t be included in planned implementation, or is included but goes to all implementations


## Approach 2 - Users add options by nesting options within the component

#### Implementation Example:
```
<abds-select>
    <option value="one">alpha</option>
    <option value="two">beta</option>
    <option value="three">gamma</option>
</abds-select>
```

### Pros
- Feels more natural to add the options as tags in the html, closer to experience with native HTML `select`
- Looks good, works well with linters + formatters
- Can use familiar methods such as map to create options dynamically
- Easy to add custom attributes like unique keys for React

### Cons
- POC needed to check viability of this approach - are options showing up within the `select` dropdown? Will it be possible to associate the options via named slots?



## Common issues to Both Approaches

- Shadow dom + form submission - right now nothing is associated in the light with select to be submitted
   - most likely approach will be an invisible element in the light to match each visible option in the shadow, and that value is what is submitted
   - similar to our radio/checkbox and calcite’s approach
Angular - who knows


