# References
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button
https://www.lightningdesignsystem.com/components/button-icons/
https://carbondesignsystem.com/components/button/usage/#icon-only-buttons
https://garden.zendesk.com/components/icon-button
https://rei.github.io/rei-cedar-docs/components/buttons/#use-when
https://designsystem.morningstar.com/components/button/?tab=design#use-when
https://m3.material.io/components/icon-buttons/guidelines
https://gestalt.pinterest.systems/web/iconbutton#Best-practices
https://design.gitlab.com/components/button#icons

## Intro description
> A button icon lets users take an action and uses visual iconography to convey the action that will occur.

> Button icons provide the user with visual iconography that is typically used to invoke an event or action.

> Button icons are button elements that represent their behavior with an icon instead of text.

> Buttons are used to initialize an action. Button icons express what action will occur when the user interacts with it.

> Icon buttons (like Buttons) let users take action. They are used for repeated or persistent actions on a page and lack visible labels to simplify the UI.

> A Button is a clickable element which communicates that users can trigger an action.

> Icon buttons help people take supplementary actions with a single tap. They’re used when a compact button is required, such as in a toolbar or image list.

## Usage
> Buttons are clickable elements that are used to trigger actions. They communicate calls to action to the user and allow users to interact with pages in a variety of ways. Button labels express what action will occur when the user interacts with it.

> Buttons communicate actions that users can take. They are typically placed throughout your UI, in places like: Dialogs, Forms, Toolbars, etc.

> The <button> HTML element is an interactive element activated by a user with a mouse, keyboard, finger, voice command, or other assistive technology. Once activated, it then performs a programmable action, such as submitting a form or opening a dialog.

> Use icon buttons to display actions in a compact layout. Icon buttons can represent opening actions such as opening an overflow menu or search, or represent binary actions that can be toggled on and off, such as favorite or bookmark.
> Icon buttons can be grouped together or they can stand alone.

## Use when
- To simplify the appearance of repeated or persistent actions on a page
- To enable action in a toolbar

---
- Submit a form
- Begin a new task
- Trigger a new UI element to appear on the page
- Specify a new or next step in a process

---
- Affording interaction to key behaviors and features.
- Confirming or submitting information entered into a form.
- Cancelling an action.
- Resetting a form or dataset.
- Closing a container or section.
- Opening a popover.
- Moving forward or backward through a stepper workflow.
- Creating an object within a group.
- Applying a non-critical action to a dataset.

---
- Triggering an action
- Enabling a “final” action
- Progressing or regressing a user through a step in a flow
- Submitting requested information
- Confirming the completion of a flow or cancelling out of it
- Use tag="a" and href when navigating to another page on the site

## Don't use when
- To enable primary and secondary actions on a page, use a Button instead

---
- Displaying a collection of links to sections. Use links instead.
- Linking to an external site. Use links instead.

---
- Taking users to a different part within the same page. Instead, use Links

## Accessibility
> Buttons that only show an icon to represent do not have an accessible name.
> To give an icon button an accessible name, put text in the <button> element that concisely describes the button's functionality.

> If an icon button doesn’t include a label, use a title attribute to show on hover for sighted users, and a span with class slds-assistive-text to describe the button's action for screen readers.
> When using assistive text, the icon element itself should have `aria-hidden` set to `true`.