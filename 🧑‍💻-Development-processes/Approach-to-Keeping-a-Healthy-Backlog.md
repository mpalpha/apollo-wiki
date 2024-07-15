Working towards a healthy backlog required regularly reviewing the backlog items, creating clear acceptance criteria and decomposing the items into smaller units of work for execution.  A pattern that we have been following has been:

1. Prepare the feature by defining the acceptance criteria
3. Define a backlog item for the MVP of that feature as a subset of the feature's acceptance criteria
4. Define additional functionality in separate backlog items that can be executed independently.


## Prepare the Feature

1. Look at the design in Figma
2. Understand the context of use
    1. Understand how end users will interact with the component 
        - check zeroheight for design intent
        - check atlassian ds for possible intent (if needed)
        - check lightning ds for possible intent (if needed)
    2. Understand how implementors will use the component
    3.  Get with Tuan if it isn’t clear
3. Identify variations in the visual design that can be expressed as configurable properties e.g. palette
4. Identify variations in the behavior that can be expressed as configurable properties e.g. dismissible
5. Express these as acceptance criteria: 
    1. Users shall be able to…
        - e.g press a button and x happens
        - e.g. enter a value greater than the maxlength
    2. Implementors shall be able to…
        - e.g. specify a palette that styles the color and border of the component
        - e.g. specify a callback for the click event

Note: In general, try to stay away from implementation details at this point.  Make sure you know what needs to be accomplished and why before tackling how it should be done.

Other Notes:
When in doubt, bust keynote out.

## Define MVP
A MVP component is analogous to a MVP product feature; a version of a product (component) with just enough features to be usable by early customers (adopters) who can then provide feedback for future improvements.  

Determining what acceptance criteria represent the MVP of a component often requires input from the entire team.

From the Feature's acceptance criteria, take a subset of features that represent the MVP and create a new Backlog item.

## Additional Functionality

Acceptance criteria that are not included in the MVP should be put into additional Backlog items.  An important criteria creating Backlog items is that the work can be completed independently of other Backlog items.  For more about creating quality Backlog items, the see the [INVEST principle](https://www.agilealliance.org/glossary/invest/)
 