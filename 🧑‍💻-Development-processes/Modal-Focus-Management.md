A modal dialog is a dialog that appears on top of the main content and moves the system into a special mode requiring user interaction. This dialog disables the main content until the user explicitly interacts with the modal dialog

To accomplish this requires attention to the management of keyboard focus:

**Focus Trap** - The dialog's tab order wraps, which means that when the user tabs through the focusable elements in the dialog, the first focusable element will be focused after the last one has been reached. In other words, the tab order should be contained within and by the dialog.


**Focus Return**  - Focus After the dialog is dismissed, keyboard focus should be moved back to where it was before it moved into the dialog. Otherwise the focus can be dropped to the beginning of the page.


##Focus Trap

**dialog.openModal()**
An experimental feature of the HTMLDialogElement interface could provide much of the focus trap functionality out of the box.  However, it is not recommended after failed testing in FF v99.  Testing failed because stencil components cannot implement the HTMLDialogElement interface.
https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement#browser_compatibility

**FAST Components**
Microsoft's FAST doesn't actually have a modal component, but treats a modal as a variant of a dialog.
https://explore.fast.design/components/fast-dialog

It traps focus on the modal by adding an event listener to the document.


**Calcite**
Calcite uses what it calls a "focus-fence" structured roughly like so:

```
<modal>
  <div focus-fence ></div> 

 
    ...modal content 

 
  <div focus-fence></div>
 
</modal>
```

Each focusFence has a `tabindex="0"` and an `onFocus` event.  The modal "traps" the focus to the modal by forwarding focus to the first focus-fence when the last focus-fence gets focus.

The modal forwards focus to the first focusable element, or to the modal close button, when the first focus-fence gets focus
https://github.com/Esri/calcite-components/blob/master/src/components/modal/modal.tsx

![Screen Shot 2022-03-18 at 9.41.42 AM.png](/.attachments/Screen%20Shot%202022-03-18%20at%209.41.42%20AM-a6aac1c3-b173-491f-9472-7542143b5665.png)

Simple implementation example here: https://webcomponents.dev/edit/oqglMrFG29jDHnuc1dLn/src/index.tsx?p=stories

##Focus Return

**Calcite**
Calcite saves a reference to the `document.activeElement` when the modal is opened in a private variable `previousActiveElement`

Focus is returned to `previousActiveElement`when the dialog is closed.

https://github.com/Esri/calcite-components/blob/master/src/components/modal/modal.tsx

##Recommendation
Calcite has a straightforward, isolated implementation of focus trap and focus return with the lowest level of effort.  Recommend moving forward with an implementation similar to calcite's.
