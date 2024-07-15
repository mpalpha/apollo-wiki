[Date input icon spike:  ](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_workitems/edit/571) Can we use a custom icon with native date picker, and if so how can we do that with cross browser support?

The chart below shows the default behavior of in different browsers.

![Screen Shot 2022-01-06 at 10.37.53 AM.png](/.attachments/Screen%20Shot%202022-01-06%20at%2010.37.53%20AM-5ce45686-b554-4700-8f3f-fd3328ac4aac.png)

## Notes on behavior: 
Firefox: 
- Date picker calendar appears when the **input** is clicked.
- No default icon but a _clear input_ icon &#9447; is displayed once a value is selected .

### Chrome/Edge
- Date picker calendar appears when the icon is clicked.
- Calendar icon is always present 

### Safari
Date picker calendar appears when the input is clicked.
No default icon

## Recommendation

Position a custom icon over the default calendar picker indicator (either grid or absolute position).  Then set the calendar icon to `pointer-events: none` which will cause all click events to be passed through to the calendar picker indicator underneath. From stackoverflow answer:   https://stackoverflow.com/a/44604144/981556

Advantage: 
- Preserves the browser specific behavior of triggering the date picker
- Low development effort

Disadvantages
- Removes Firefox's clear input icon 

Examples below show that icon placement is consistent enough to avoid browser specific positioning.

![Screen Shot 2022-01-06 at 10.48.59 AM.png](/.attachments/Screen%20Shot%202022-01-06%20at%2010.48.59%20AM-fd2f6f3c-87be-4c70-84cb-1866fed5e3aa.png)