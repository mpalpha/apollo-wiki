# Button treatments

For the `abds-button` component, `appearance` and `palette` attributes are used to configure each button treatment below.

## Basic

Use this treatment for a button that resembles a plain text link while retaining button container dimensions. This button may be used frequently on a page and even multiple times per module. Use it when the button action is of secondary importance to the content surrounding it.

- `appearance="transparent"`
- `palette="brand"`

[https://master--61522e2345c74a004a984ee1.chromatic.com/?path=/docs/components-buttons-basic--basic]()

## Neutral

Use this treatment for a more discernible button than Basic. This button may be used frequently on a page and even multiple times per module. Use it when the button action is of secondary importance to the content surrounding it.

- `appearance="outline"`
- `palette="neutral"`

[https://master--61522e2345c74a004a984ee1.chromatic.com?path=/docs/components-buttons-neutral--neutral]()

## Brand

Use this treatment for a very high contrast button on light backgrounds. This button should be used sparingly, to represent a primary action that stands out and is clearly more important than other actions on a page or module.

- `appearance="solid"`
- `palette="brand"`

[https://master--61522e2345c74a004a984ee1.chromatic.com?path=/docs/components-buttons-brand--brand]()

## Brand outline

Use this treatment for a button with higher contrast than Basic or Neutral, but less contrast than Brand. This button may be used multiple times on a page but less frequently than Basic or Neutral buttons. It may be used for primary or secondary actions.

- `appearance="outline"`
- `palette="brand"`

[https://master--61522e2345c74a004a984ee1.chromatic.com?path=/docs/components-buttons-brand-outline--brand-outline]()

## Inverse

Use this treatment for a high contrast button on dark backgrounds. This button should be used sparingly for primary or secondary actions.

- `appearance="outline"`
- `palette="inverse"`

[https://master--61522e2345c74a004a984ee1.chromatic.com?path=/docs/components-buttons-inverse--inverse]()

## Destructive

Use this treatment for a high contrast button that represents a destructive action (e.g. permanently erasing data). This button should be used sparingly, for a primary (destructive) action that stands out on a page or module.

- `appearance="solid"`
- `palette="destructive"`

[https://master--61522e2345c74a004a984ee1.chromatic.com?path=/docs/components-buttons-destructive--destructive]()

## Destructive outline

Use this treatment for a destructive action button with less contrast than Destructive. This button should be used sparingly, for primary or secondary (destructive) actions on a page or module.

- `appearance="outline"`
- `palette="destructive"`

[https://master--61522e2345c74a004a984ee1.chromatic.com?path=/docs/components-buttons-destructive-outline--destructive-outline]()

## Success

Use this treatment for a high contrast button that represents a positive action (e.g. completing an order). This button should be used sparingly, for a primary action that stands out on a page or module.

- `appearance="solid"`
- `palette="success"`

[https://master--61522e2345c74a004a984ee1.chromatic.com?path=/docs/components-buttons-success--success]()


# Button with icon

An icon can both clarify a button’s action and call attention to it. Refer to the usage guidelines for more details on appropriate use.

## Leading icon

To display a leading icon before text, add an `icon-start` attribute with the name of the icon to the `abds-button` component.

- `icon-start="calendar"`

[https://master--61522e2345c74a004a984ee1.chromatic.com/?path=/docs/components-buttons-with-icon-start--with-icon-start]()

## Trailing icon

To display a trailing icon after text, add an `icon-end` attribute with the name of the icon to the `abds-button` component.

- `icon-end="calendar"`

[https://master--61522e2345c74a004a984ee1.chromatic.com/?path=/docs/components-buttons-with-icon-end--with-icon-end]()

# Full-width button

By default, the width of a button is set to auto which dynamically changes based on its inner contents. To display a button that fills the width of its container, set the attribute to `full`:

- `width="full"`

[https://master--61522e2345c74a004a984ee1.chromatic.com/?path=/docs/components-buttons-full-width--full-width]()


# Interactive playground

Preview different buttons and attributes using the interactive widget below.

[https://master--61522e2345c74a004a984ee1.chromatic.com?path=/docs/components-buttons-interactive--interactive]()