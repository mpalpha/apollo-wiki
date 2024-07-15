
Two techniques for querying slotted content have been demonstrated, each with different results.  This document explains the techniques and highlights their differences.

`this.host.children` - returns a live collection
`this.host.shadowRoot.querySelector()` - returns a static collection

[Live vs Static Nodelists on MDN](https://developer.mozilla.org/en-US/docs/Web/API/NodeList#live_vs._static_nodelists)


## Getting slot content with **`this.host.shadowRoot.querySelector()`**

Lifecycle methods:
- componentDidRender
- componentDidLoad
- componentShouldUpdate
- componentWillUpdate
- componentWillRender**
- componentDidUpdate

Returns: NodeList (static)

The SlotElement will return `null` in the `connectedCallback`, `componentWillLoad`, and in the initial call to `componentWillRender`

Items in the NodeList are the `slot` elements from the shadow dom.  

A nodeList looks like this when logged in the console:
`NodeList(11) [slot, slot, slot, slot, slot, slot, slot, slot, slot, slot, slot]`

Target light dom rendered nodes in the NodeList with the `childNodes` property.

This is the technique found in the [stencil documentation](https://stenciljs.com/docs/styling#shadow-dom-queryselector)

Documentation for [NodeList](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)

Also see example on the **shadowroot-query-and-report** branch on [webcomponents.dev](https://webcomponents.dev/edit/UDXpjjUZGoJY2k0a6yJ1)

## Getting slot content with **`this.host.children`**

Lifecycle methods:  
- **any**

Returns: a **live** HTMLCollection

The items in the collection are Elements from the light dom rendered into slots, both default and named.  _Textnodes are not included in the collection._  

An html collection looks like this when logged in the console:
`HTMLCollection(10) [h1, div, div, div, div, div, div, div, div, div]`

Target a slot or slots within the HTMLCollection with the **item()** or **namedItem()** method to select a node within the collection

Alternatively, construct an Array from the collection with `Array.from()` and use array methods on the collection

example:  `Array.from(this.host.children).filter((slot) => slot.getAttribute('slot') === 'modal-body')[0];`

This is the technique used in calcite's dom utils (https://github.com/Esri/calcite-components/blob/master/src/utils/dom.ts  see getSlotted)

Documentation for [HTMLCollection](https://developer.mozilla.org/en-US/docs/Web/API/HTMLCollection)

Also see example on the **hostchildren-collection** branch on [webcomponents.dev](https://webcomponents.dev/edit/UDXpjjUZGoJY2k0a6yJ1)

## Recommendation

Use `this.host.children` when you need access to slotted content before an the initial render of the component.