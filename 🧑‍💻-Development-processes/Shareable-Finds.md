The purpose of this document is for us to share things you might think are useful for others to know.

# Stencil
* Props in web components are not case sensitive so if a prop's name is `text`, you can also pass a value by using `tExT`

# Storybook
* Storybook interprets the `|` character to mean separate distinct values in a list. It does this in all cases. For example, demonstrating that the default value for a component's interactive story's control is a `|` will yield in the default value being represented as empty string `""`. Storybook parses the `|` away, and leaves an empty string in its place.
* In the **argTypes** **description**, add a line break by placing a newline character `\n` at the beginning of text on its own line.
* In the **argTypes** **description**, add code blocks by placing `\n\n\t` between text preceding the code and the code itself. 

# Testing

### Want to see how your test run on a real browser instance?

In `apollo/packages/components/stencil.config.ts` add the following property to the `config`:

`testing: { browserHeadless: false },`

**_Note:_** Other options like `browserDevtools` and `browserSlowMo` are available, though there is a [current open defect](https://github.com/ionic-team/stencil/issues/2237) on `browserSlowMo`

### Want to watch changes on a specific test file?
In `apollo/packages/components/package.json` modify the `scripts` object to something similar:

```"test:watch": "stencil test --e2e 'src/components/switch/tests/switch.e2e.ts'"```

**_Note:_** You can run this on spec tests as well with `--spec`

### Want to test focus state or other accessibility options?
Puppeteer has an accessibility/snapshot class you can access and test against. [Click here to learn more](https://github.com/puppeteer/puppeteer/blob/main/docs/api.md#class-accessibility)

# VS Code

### Extensions 
[Highlight Matching Tag](https://marketplace.visualstudio.com/items?itemName=vincaslt.highlight-matching-tag) - Highlights matching opening and/or closing tags

[Restore Terminals](https://marketplace.visualstudio.com/items?itemName=EthanSK.restore-terminals) - Automatically spawn integrated terminal windows and split terminals, and run any shell commands when VSCode starts up!

### Tricks

Problem: I mainly work on 2 or 3 files at a time, but end up opening more and my main ones get lost

Solution: In the tab section, right click on the file you want to keep. Click on 'Pin'. This will put all pinned files to the right. If you accidentally click the close all icon ![image.png](/.attachments/image-ffb3060c-c0f0-4f47-8f62-91fda4f6d517.png) it will still keep those pinned files for you

# Random

### CSS
When hover and an active state is desired on an element. The active class should go after the hover class like so:
```
.container {
    @apply hover:bg-brand-600;
    @apply active:bg-brand-700;
}
```