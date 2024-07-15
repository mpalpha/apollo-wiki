# Use case

Allow users to quickly toggle the state of a single option. Compared to a checkbox, a switch change usually takes effect immediately, without any additional submission.

---

# Acceptance criteria

## **Visual**

### Figma URL:
https://www.figma.com/file/9XtGGfUck6iDFiAoh0iYBO/?node-id=1%3A15

### Anatomy
- [x] Control (input)
  - [x] Track
  - [x] Thumb
  - [x] Icon checked
  - [x] Icon unchecked
- [x] Label (optional)
- [x] Icon tooltip (optional)

### Theme variants:
- [x] Base

### Styles

#### Layout/spacing (position, margin, padding, alignment, display, grid, flex)
- [x] Track
- [x] Thumb off
- [x] Thumb on
- [x] Icon checked
- [x] Icon unchecked
- [x] Label on right
- [x] Label multi-line
- [ ] Label on left (TODO)
- [x] Icon tooltip

#### Size (width, height)
- [x] Track
- [x] Thumb

#### Font (color, family, size, weight, line height, letter spacing, text decoration)
- [x] Label

#### Iconography (svg, color, size, stroke width)
- [x] Icon checked
- [x] Icon unchecked
- [x] Icon tooltip

#### Background color
- [x] Track off
- [x] Thumb off
- [x] Track on
- [x] Thumb on

#### Border (color, radius, width)
- [x] Track
- [x] Thumb

#### Outline/focus ring (color, width, style)
- [x] Track
- [ ] Icon tooltip

#### Elevation (shadow, z-index)
- [x] N/A

#### Animation (transition, animation)
- [x] Track
- [x] Thumb
- [ ] Icon tooltip

#### Cursor
- [x] Control (track, thumb, icons)
- [x] Label
- [ ] Icon tooltip

### States

#### Off/Unchecked
- [x] Thumb on left
- [x] Icon unchecked

#### On/Checked
- [x] Thumb on right
- [x] Icon checked

#### Hover (not disabled)
- [x] Track
  - [x] Background color
- [ ] Icon tooltip
  - [ ] Color

#### Active (not disabled)
- [x] Track
  - [x] Background color
  - [x] Focus ring
- [ ] Icon tooltip
  - [ ] Focus ring

#### Focus (not disabled)
- [x] Track
  - [x] Focus ring
- [ ] Icon tooltip
  - [ ] Focus ring

#### Disabled
- [x] Track
  - [x] Background color
- [x] Thumb
  - [x] Background color
- [x] Icon checked
  - [x] Color
- [x] Icon unchecked
  - [x] Color
- [x] Control (track, thumb, icons)
  - [x] Cursor
- [x] Label
  - [x] Cursor

## **Behavior**

### Behavior in response to user interaction

#### Hover
- [x] Hover on control displays hover state
- [x] Hover on control displays pointer/hand cursor
- [x] Hover on label displays pointer/hand cursor

#### Active
- [x] Mouse press (and hold) on control displays active state and focus state
- [ ] When control is focused, press (and hold) the `space` key displays active state

#### Focus
- [x] Gains focus with click on control
- [x] Gains focus with click on label
- [x] Gains focus with the `tab` key
- [x] Focus ring is visible on the control (not the label)

#### Blur
- [x] Loses focus with click outside of switch
- [x] Loses focus with the `tab` key
- [ ] ~~Runs inline input validation~~ N/A

#### Off/Unchecked
- [x] Toggled with click event
- [x] Toggled with `space` key (down and up) event
- [x] Displays icon unchecked

#### On/Checked
- [x] Toggled with click event
- [x] Toggled with `space` key (down and up) event
- [x] Displays icon checked

#### Disabled
- [x] Retains current checked/unchecked state
- [x] No hover or focus events or click allowed
- [x] Cursor on hover should be `not-allowed` or `default`

#### Validation
- [ ] ~~Switch shall implement constraint validation rules consistent with native inputs~~ N/A
  - [ ] ~~Display the error state and error text if user input fails validation through the following approaches:~~
    - [ ] ~~After submit~~
    - [ ] ~~On focus change~~
    - [ ] ~~Remove the error state and error text if user input passes validation through the above approaches~~

### Behavior in response to changes in data/system feedback

## **Functionality**
- [x] Switch can function without a label (support use cases with custom labels)
- [ ] Switch should follow conventions established in checkbox/radio
  - [ ] Hidden input to allow custom elements to be available to the browser as a form control
  - [ ] Label-able

## **Accessibility**

### WCAG threshold (2.0/2.1, AA, AAA)
- [ ] Switch shall be associated with a label unless implemented with a custom label
- [x] Contrast ratio of at least 3:1 to differentiate graphical objects (WCAG 2.1
Level AA)

### Tab indices
- [x] Focusable and keyboard accessible

### ARIA
- [ ] `role="switch"` attribute (it's unclear if we should use the "switch" aria role - there seem to be inconsistencies in the functionality of the switch role)
- [ ] `aria-checked` attribute (required with `switch` role)

## **API configuration**
- [x] label text (optional)*
  - [ ] \*alternate label or aria attribute required for accessibility
- [x] tooltip text (optional: displays icon tooltip control when present)
- [x] checked state is configurable from outside
- [x] disabled
- [x] value
- [x] name
- [x] no support for required
- [x] no support for indeterminate

---

# Dependencies

- Icon component
- Label component
- Tooltip component

---

# Board

Feature: #115

---

# References

## Implementation references

- https://www.sarasoueidan.com/blog/toggle-switch-design/ (2 radios approach)
- https://inclusive-components.design/toggle-button/ (toggle button approach)

## Accessibility references

- https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/switch_role