# Best practices

### Naming
- Test names should read naturally and say what the test is and what it expects
- On the `describe` section, you might want to keep it generic to just the component name so that it plays nice with the `it` tests below it
- Example:
  - Describe: `abds-checkbox`
  - It: `renders as checked when the checked property is passed`
  - When the test is running and it fails, it reads like this: `abds-checkbox › renders as checked when the checked property is passed`

### E2E test
Here are some of the best practices for End to End testing:
- Use `async` and `await` since most methods are async and return promises
- `await page.waitForChanges()` should used after you trigger an action to change the component's state
- Use the `>>>` piercing selector to find an element inside a component's shadow root
  - Example usage it in our checkbox component: `const tooltipElement = await page.find('abds-label >>> abds-icon');`
- For E2E tests you can directly interact with the window object as you normally would since it is a chromium instance


[See the full list of tips in StencilJS](https://stenciljs.com/docs/end-to-end-testing)

To see what methods are available in `newE2EPage` you can search for `E2EPage`/`NewE2EPageOptions` in `node_modules/@stencil/core/testing/puppeteer/puppeteer-declarations.d.ts`

E2E test setup pattern:

```
import { E2EPage, newE2EPage } from '@stencil/core/testing';
import { Checkbox } from '../checkbox';

const getPage = async (
  { alignment, checked, disabled, indeterminate, name, required, tooltip, value }: Partial<Checkbox> = {},
  children = ''
): Promise<E2EPage> => {
  const page = await newE2EPage();
  await page.setContent(`
    <abds-checkbox
      ${alignment ? `alignment=${alignment}` : ''}
      ${checked ? 'checked' : ''}
      ${disabled ? 'disabled' : ''}
      ${indeterminate ? 'indeterminate' : ''}
      ${name ? `name=${name}` : ''}
      ${required ? 'required' : ''}
      ${tooltip ? `tooltip=${tooltip}` : ''}
      ${value ? `value=${value}` : ''}
    >${children}</abds-checkbox>
  `);

  return await page;
};

describe('abds-checkbox', () => {
  it('renders as checked when the checked property is passed', async () => {
    const page = await getPage({checked: true});
    // `getPage` function takes an object with props you can override
    // This avoids duplicating code to mount components
  });
});
```

### Unit test (Spec)
It was decided as a team to apply spec tests on component by component basis.We should at least have 1 spec test per component to catch scenarios where the markup changes

For spec tests you can modify the window object and reference it by the returned "page" object from `newSpecPage()`. Example:
```
import { newSpecPage } from '@stencil/core/testing';
import { Checkbox } from '../checkbox';

const page = await newSpecPage({
    components: [Checkbox],
    html: `<abds-checkbox></abds-checkbox>`,
});

console.log('Mock testing window: ', page.win);
```
Using `page` variable from above the following are also available in spec tests:
- `page.body`: Mocked testing `document.body`
- `page.doc`: Mocked testing document
- `page.root`: The first component found within the mocked `document.body`
- `page.rootInstance`: Component instance, if a root component was not found it'll return null

To see what methods are available in `newSpecPage` you can search for `SpecPage`/`NewSpecPageOptions` in `node_modules/@stencil/core/internal/stencil-private.d.ts`. Or [see Stencil's documentation on options](https://stenciljs.com/docs/unit-testing#:~:text=The%20newSpecPage(options)%20method%20takes%20an%20options%20argument%20to%20help%20write%20tests%3A)

###Config

Global config can be set with a `jest.config.js file` in the root of the project if needed. By default we get this setup:
```
module.exports = {
  globalSetup: './setup.js',
  globalTeardown: './teardown.js',
  testEnvironment: './puppeteer_environment.js',
};
```

###Code Snippets
Modify the following script in `components/package.json` to watch individual tests/files:

`"test:watch": "STENCIL_PROD=true && stencil test --e2e --watchAll ./components/select"`

Modify config object in `components/stencil.config.ts` to see tests run in a browser:
```
  testing: {
    browserHeadless: false,
    browserSlowMo: 5000,
  }
```

Logout the body of the page
```
const bodyHTML = await page.evaluate(() => document.querySelector('body').innerHTML);
console.log({ bodyHTML });
```

Sometimes it's also helpful to logout the outerHTML and shadowroot of a web component to see its fully rendered markup:
```
const abdsComponent = await page.evaluate(() => ({
  outerHTML: document.querySelector('abds-component').outerHTML,
  shadowRoot: document.querySelector('abds-component').shadowRoot.innerHTML,
}));
console.log(abdsComponent);
```

###Debugging
For logging objects, parse using JSON.stringify (e.g. `console.log(JSON.stringify(someObject))`).










