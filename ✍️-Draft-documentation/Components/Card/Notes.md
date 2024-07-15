# References:

https://www.lightningdesignsystem.com/components/cards/

Description
> Cards are used to apply a container around a related grouping of information.

A11y
> Cards should use an underlying <article> element to maintain usability for some screen reader users.

> The card heading level should follow the DOM structure of the page. We are using h2 as the default heading level for examples, but real world use will dictate the correct level based on the surrounding elements.

https://spectrum.adobe.com/page/cards/

Description
> Cards group information into flexible containers to let users to browse a collection of related items and actions. They show a taste of information and reveal more details upon interaction.



https://material.io/components/cards
https://m3.material.io/components/cards/guidelines
https://design.gs.com/components/card
https://polaris.shopify.com/components/card
https://design.gitlab.com/components/card
https://designsystem.digital.gov/components/card/
https://designsystem.morningstar.com/components/card/?version=4.0.2&tab=design
https://paste.twilio.design/components/card
https://design-system.hpe.design/components/card
https://baseweb.design/components/message-card/
https://designsystem.quickbooks.com/component/cards/
https://clarity.design/documentation/cards
https://www.nutrien.design/97a80fae9/p/50b213-cards/b/485d09

~~https://carbondesignsystem.com/components/tile/usage/~~
~~https://www.ibm.com/standards/carbon/components/card/~~


# Figma component comments:

T:
> Hey Ben Radcliffe, the hover state of a card only applies when the whole card is clickable, right? If a card is not interactive, then it really shouldn't have a hover state, imo.

B:
> Yes, in fact, this is another pseudoclass that is a remnant of v2 I've been deliberating on purging. If a card is a call to action, then it should have a distinct call to action in the form of a button, which itself conveys the hover state and is focusable. It's why I nuked all of the focus variants.
Your input validates my thoughts, so if you're okay with it, we can proceed to delete the hover property and variants.

T:
> As much as I'd like to agree with that, many ecommerce sites display lists of items as cards that are clickable without a button. A page with a grid of cards that repeat the same action button(s) might even look too busy and repetitive.
So I think we should allow a card to be a cta, but only allow hover, active, and focus states on variants with no buttons.

B:
> My concern with allowing a card to be a CTA is that it introduces a lot of accessibility complexity. Now it's behaving as a button, has a different role, and requires a much different implementation for ARIA.
I'd say it's good to keep in mind, but we'll need to document it and run it past the devs.

T:
> What if a card is wrapped in an anchor tag, so it's a simple link? That's probably the most common use case.

B:
> Then it needs a clear CTA, so I'd enforce a button. Making a whole thing clickable when there are discrete elements in the DOM to do so is not the greatest practice. See here: https://ux.stackexchange.com/questions/133849/card-with-button-or-completely-clickable-card

T:
> It makes some great points, yes. But if a card has no button and is not clickable, then it's just a static info card, in which case, it probably shouldn't have any elevation, imo. Elevation is often a visual cue for interactivity.

B:
> To a point. I believe that elevation only implies interactivity when tied to microinteractions. A change in elevation would imply this, not a static card having a box shadow.
That's why I'm rather for removing the "hovered" state of cards.

T:
> Okay. This discussion and the stackexchange link will help with our guidance for cards on zeroheight.

T:
> Sorry, just one last comment: I think a clickable link card with a headline and short paragraph could provide more context for users of screen readers than buttons that say "learn more" or "view details." If a card has a lot of text, then for sure a CTA is better. But most cards will have brief summary info.