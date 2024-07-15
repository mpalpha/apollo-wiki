# Design usage

Buttons communicate actions that users can take. They are commonly used in user interfaces, in places like:

- Pages
- Modals
- Forms
- Cards
- Toolbars

## In Figma

You can find the component to use in your designs by choosing:

- **Assets → Components, v3\* → Button**

  Designed to have dynamic width based on its inner contents (i.e. inline)

- **Assets → Components, v3\* → Button block**

  Designed to have flexible width that can fill its container

Create an instance of the component by simply dragging it onto your canvas. You can select different variants (treatment, state, etc) of the component from the Instance properties panel on the right sidebar.

<mark>*If you don’t see Components, v3 in the Assets panel, refer to the Getting Started guide on how to add it to your Figma library.</mark>

# Treatments

- **Basic**
Use this treatment for a button that resembles a plain text link while retaining button container dimensions. This button may be used frequently on a page and even multiple times per module. Use it when the button action is of secondary importance to the content surrounding it.

- **Neutral**
Use this treatment for a more discernible button than Basic. This button may be used frequently on a page and even multiple times per module. Use it when the button action is of secondary importance to the content surrounding it.

- **Brand**
Use this treatment for a very high contrast button on light backgrounds. This button should be used sparingly, to represent a primary action that stands out and is clearly more important than other actions on a page or module.

- **Brand outline**
Use this treatment for a button with higher contrast than Basic or Neutral, but less contrast than Brand. This button may be used multiple times on a page but less frequently than Basic or Neutral buttons. It may be used for primary or secondary actions.

- **Inverse**
Use this treatment for a high contrast button on dark backgrounds. This button should be used sparingly for primary or secondary actions.

- **Destructive**
Use this treatment for a high contrast button that represents a destructive action (e.g. permanently erasing data). This button should be used sparingly, for a primary (destructive) action that stands out on a page or module.

- **Destructive outline**
Use this treatment for a destructive action button with less contrast than Destructive. This button should be used sparingly, for primary or secondary (destructive) actions on a page or module.

- **Success**
Use this treatment for a high contrast button that represents a positive action (e.g. completing an order). This button should be used sparingly, for a primary action that stands out on a page or module.

# States

A button can have the following interactive states: default, hover, active, focus, and disabled. The focus state can overlap with all the other states, except disabled.

- Default
- Default + Focus
- Hover
- Hover + Focus
- Active + Focus
- Disabled

# Best Practices

## **Do**

- A button’s action and state should be clear.
- Use sentence case capitalization, i.e., “Learn more” instead of “Learn More.”
- When using multiple buttons, the primary button appears to the right and any secondary buttons appear to the left.

## **Don’t**

- Don’t use a button to navigate to another place, use a link instead. The exception is in a wizard where “Back” and “Next” buttons may be used.
- Don’t put too much text in a button — try to keep the length of your text to a minimum.

# Button with icon

An icon can enhance the UX of a button when used appropriately. When placed next to a text label, it can both clarify a button’s action and call attention to it. For example, a “Delete” button that displays a trash icon can be more easily recognized by users than with just a text label alone.

## Placement

- Left icon placement
- Right icon placement

## Usage

Left vs. right icon placement depends on the action:

- In English and other left-to-right languages, it often makes more sense to place the icon left of the text for a better reading flow, such as in the “Download” button example at the top of the page.
- But there are instances where placing the icon to the right of text makes more sense, such as in the “Continue” button example at the top, which has an arrow icon to indicate going to the “next” page.

### In Figma

To show the left or right icon:

1. Select the **Button** instance and go to the Instance properties panel on the right sidebar.
1. Open the **Has icon** menu and select **Left** or **Right**.

To change the icon:

1. Double-click into the icon component until the **SVG** layer is selected (or expand the **Button** component in the Layers panel to find the **SVG** layer).
1. In the Instance properties panel on the right sidebar, click on the **calendar** dropdown to bring up the **Swap Instance** menu.
1. Scroll to find your desired icon or search by keyword. Then click to select your new icon. (If you don’t see a list of other icons in the Swap Instance menu, then click on the button to the right of search and select **Foundations, v3** followed by **Streamline icons**.)

## Best Practices

#### **Do**

- Use icons that clearly communicate their meaning.

#### **Don’t**

- Don’t vertically stack an icon and text in the center of a contained button.
- Don’t use two icons in the same button.