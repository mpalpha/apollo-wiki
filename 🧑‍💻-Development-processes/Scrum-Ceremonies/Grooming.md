## Grooming Purpose:
Ensure the next few sprints worth of user stories in the product backlog are prepared for sprint planning and are ready to be picked up.

Working towards a healthy backlog required regularly reviewing the backlog items, creating clear acceptance criteria and decomposing the items into smaller units of work for execution. A pattern that we have been following has been:

1. Prepare the feature by defining the acceptance criteria.
3. Define a backlog item for the MVP of that feature as a subset of the feature's acceptance criteria.
4. Define additional functionality in separate backlog items that can be executed independently.

## How to prepare
1. On Monday's standup, ask the team what component should be groomed next.
2. In "🕸 Web" -> "Meeting Notes" -> "Backlog Grooming", Add a new section with the component(s) to be groomed for the upcoming session.
3. Create a story task under an evergreen feature if one does not currently exist.
4. Look at the design in Figma.
5. Understand the context of use.
    1. Understand how end users will interact with the component .
        - check zeroheight for design intent.
        - check atlassian ds for possible intent (if needed).
        - check lightning ds for possible intent (if needed).
    2. Understand how implementors will use the component.
    3.  Get with Design if it isn’t clear.
6. Identify variations in the visual design that can be expressed as configurable properties e.g. palette.
7. Identify variations in the behavior that can be expressed as configurable properties e.g. dismissible.
8. Express these as acceptance criteria: 
    1. Users shall be able to…
        - e.g press a button and x happens.
        - e.g. enter a value greater than the maxlength.
    2. Implementors shall be able to…
        - e.g. specify a palette that styles the color and border of the component.
        - e.g. specify a callback for the click event.

Note: In general, try to stay away from implementation details at this point.  Make sure you know what needs to be accomplished and why before tackling how it should be done.

## Lead duties during meeting
1. Share your screen.
2. Walk through the story you prepared.
   - Make sure the team understands what the intention of the component/feature is.
3. Ask questions to the team/design that were unclear as you prepared it.
   - Your job is not to come up with the questions/answers but more of a meeting mediator to ensure the team does not get lost in implementation details.
4. Ask: "Is this feature ready for someone to pick it up?".
   - If yes, you are done.
   - If no, continue to get clarification.
5. Define what MVP features should be included.
   - Mark features/configuration as "future feature".
6. Create a new MVP backlog item.
   - Take a subset of features that represent the MVP and place inside of the new item's "Acceptance Criteria".
7. Create the following subtasks on the new MVP backlog item:
   - Meet with design before component dev begins
   - Component code
     - Purpose: Create initial component that meets the acceptance criteria for MVP.
   - Meet with design to review props and list example stories
   - Storybook stories
     - Purpose: Create Storybook stories that cover common examples of component.
   - Accessibility
     - Purpose: Make component meet WCAG 2.0/2.1 AA criteria
   - Unit tests
     - Purpose: Create E2E and Spec tests that cover the functionality of the component.
   - Example app testing
     - Purpose: Implement component in a real life scenario and test different configurations.
   - ZH documentation
     - Purpose: Create documentation in ZH that better explains component functionality/usage.


## Additional Functionality

Acceptance criteria that are not included in the MVP should be put into additional Backlog items.  An important criteria creating Backlog items is that the work can be completed independently of other Backlog items.  For more about creating quality Backlog items, the see the [INVEST principle](https://www.agilealliance.org/glossary/invest/).
 

##Post meeting lead duties
1. In "🕸 Web" -> "Meeting Notes" -> "PI Planning" , add "- groomed" to components that were completely groomed.
