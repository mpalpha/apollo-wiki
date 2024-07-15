https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button
https://www.lightningdesignsystem.com/components/buttons/
https://design.gs.com/components/button
https://carbondesignsystem.com/components/button/usage/
https://spectrum.adobe.com/page/button/
https://m3.material.io/components/buttons/guidelines
https://garden.zendesk.com/components/button
https://rei.github.io/rei-cedar-docs/components/buttons/
https://designsystem.morningstar.com/components/button/
https://paste.twilio.design/components/button/
https://design-system.hpe.design/components/button
https://gestalt.pinterest.systems/web/button

---

https://clarity.design/documentation/buttons

# Placement

There are two distinct patterns when it comes to the placement of a button.

## Z Pattern

The Z-pattern is a natural way for the user to go through content within a constrained container and when tasks are oriented from the top-left and ending with a primary call to action on the right bottom side of the container. This pattern is reversed for right to left languages.

Modals and Wizards follow the Z Pattern


## F Pattern

The F-pattern is a natural way to go through content in an unconstrained container, such as a form on the page itself. The user will go through the content line-by-line, arriving at a call to action at the end.

Forms and Cards follow the F Pattern

---

https://design.gitlab.com/components/button#alignment

# Alignment

Buttons can be aligned left, right, or center depending on the context. Multiple alignments can be combined within a single screen, but not within an individual context. For example, on a single screen the main content uses left alignment, while the sidebar with multiple settings uses right alignment.

- Left alignment: In page content and forms where the content is typically unconstrained other than by the grid layout. In these instances an F-pattern (top to bottom and left to right in a horizontal movement) is common for reading flow, and buttons align with other content on the page like headings, lists, input labels, and form labels. Left alignment is a benefit for accessibility in many ways, including reading flow, focus order, and page zoom where right-aligned buttons may be initially off screen.

- Right alignment: In constrained containers like modals and dialogs, flows that continue in a progressive direction, actions with a global impact, and toolbars. In these instances a Z-pattern (top to bottom and left to right with a diagonal, scanning movement) is common for reading flow. In these instances a user may be taking a progressive action, like affirming a modal, or an action upon a section, like formatting text in a comment.

- Center alignment: Only used for empty states where content is promotional or the actions are the only ones available in context.

# Order

- Affirmative actions are positioned to the outer edge of a container. This means that on left-aligned buttons the affirmative action is the left-most action, and on right-aligned buttons, the affirmative action is the right-most action.

- An affirmative action is something that takes the users further in their journey (for example, Save or Delete), while a dismissive action takes a user back (for example, Cancel). Depending on the context, an affirmative action may be destructive.

- The visual hierarchy is primary buttons on the outer edge, followed by secondary buttons, and so on.

- One exception to the visual hierarchy is an ellipsis button. When using an ellipsis button, place it on the outer edge.

# Accessibility

- Maintain parity between focus order and visual order (don't use CSS to reorder buttons).

- When an icon is used with a text label, the icon should be hidden from screen readers with `aria-hidden="true"`.

---

https://orbit.kiwi/components/action/button/

# Buttons with icons

Buttons with icons are great when you need to draw more attention to the action. Icons add additional context and makes the buttons more easy to scan.

But it’s essential to not overuse these buttons. If everything is grabbing attention, things usually get messy.

- **Use a left icon when the button adds another item**
For cases like this, it’s great to use an icon with a plus to represent the addition, such as PlusCircle or PassengerAdd.

- **Right icons should only be directional**
They can help explain what happens when the user interacts with the button. An icon (with an aria-label) makes it easier to know if the user is taken elsewhere.

- **Add a label when using icon-only buttons**
Even the simplest icons like plus can be understood in many different ways. To make sure your icon is accessible, add a proper label to communicate the purpose.

---

https://carbondesignsystem.com/components/button/usage/#alignment

Single button:

| Alignment | Use case |
|--|--|
| Left-justified | Banner call to actions, in-page forms, and nested buttons in components like tiles |
| Right-justified | Inline notifications, inline field buttons and data tables, progressive forms, wizards, and single-button dialogs |
| Full-span | Dialogs, side panels, and small tiles; currently Carbon does not offer a way to implement full-span buttons in code, without an override, they max out at 320px |

https://carbondesignsystem.com/components/button/usage/#button-groups

**Horizontally arranged button group:**

When using multiple buttons, the position of the primary button adheres to the alignment guidance above. To sum up, a primary button will be left-aligned and positioned to the left of the secondary/tertiary button on full-page designs. The primary button will be right-aligned and appear to the right of the secondary/tertiary button within wizards and dialog windows.