This is a living document that explains how our Apollo components are tested and some of the decisions/tools we have decided to go with.

# Tools
### Unit testing
Unit tests validate the code in isolation. [See more StencilJS documentation on unit testing.](https://stenciljs.com/docs/unit-testing)

- [Jest](https://jestjs.io/docs/getting-started)

Methods like `newSpecPage()` imported from `@stencil/core/testing ` can be used to test our components as HTML. `newSpecPage()` **Does not** require a full [Puppeteer](https://pptr.dev/) instance to be running. It is also much faster. 

### Integration and E2E
E2E tests verify your components in a real browser. [See more StencilJS documentation on E2E testing.](https://stenciljs.com/docs/end-to-end-testing)
- [Jest](https://jestjs.io/docs/puppeteer)
- [Puppeteer](https://pptr.dev/)

Methods like `newE2EPage()` imported from `@stencil/core/testing ` create a headless Chromium instance where we can render our components. 

### Visual Regression Testing
- [Chromatic](https://www.chromatic.com/) - Compares new visual changes against a base build that can be approved/declined manually.

Apollo projects:
* [Master - Chromatic](https://www.chromatic.com/builds?appId=61522e2345c74a004a984ee1)
* [Release - Chromatic](https://www.chromatic.com/builds?appId=61522e2345c74a004a984ee1)

### Accessibility
- Storybook a11y plugin. [See Apollo example](https://master--61522e2345c74a004a984ee1.chromatic.com/?path=/story/components-checkbox-unchecked--unchecked
)

---