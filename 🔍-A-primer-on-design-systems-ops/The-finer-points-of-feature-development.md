# Steps Aren’t a Waterfall, But Do End Sequentially

While the workflow suggests a strict sequence, that doesn’t necessarily imply a waterfall where subsequent steps don’t begin until their predecessor ends. Instead, it’s very common to conduct steps — Design, Build, and Document — simultaneously, even if the intensity of one is driving the work.

<IMG  src="https://eightshapes.com/images/articles/design-system-features-step-by-step/3.png"  alt="Diagram of steps overlapping with many substeps annotated"/>

For example, as the design solidifies, we’ll start our Microsoft OneNote page to itemize requirements and collaborate on naming and also start to build prototype HTML and CSS to validate the design. Later on, we’ll review of draft of fully coded designs and shortly thereafter close the design step as a result.

That’s why we’ll have top-level JIRA tasks for each step, since different people may be working different steps at the same time, and each task has different reviewers (for which we use subtasks). There are other ways to model this in JIRA, but this setup works for us.

Nevertheless, the steps end sequentially, such that Design closes before Build, and Build closes before Document. Publish, at the end, is the only task that doesn’t begin until all the other steps have concluded.

# Not All Features Require Every Step

Discovery is unnecessary for many features of any self-respecting design system such as color, buttons, or form controls. Instead, each starts with design and progress through remaining steps.

<IMG  src="https://eightshapes.com/images/articles/design-system-features-step-by-step/4.png"  alt="Diagram of steps overlapping yet ending in sequence"/>

However, many other tasks use a subset of the workflow to make things. A helpful Getting Started page or description of a Contribution process requires only documentation and thus omits Design and Build:

<IMG  src="https://eightshapes.com/images/articles/design-system-features-step-by-step/5.png"  alt="Diagram of a subset of steps"/>

Similarly, UX patterns don’t result in reusable code, but can require discovery to assess cross-product relevance and needs and iterate through design ideas before being formally documented and published on a system site.

<IMG  src="https://eightshapes.com/images/articles/design-system-features-step-by-step/6.png"  alt="Diagram of a subset of steps"/>

# For Trivial Tasks, Combine Steps
Our team will also classify Figma component library development as a Design task that’s followed by combination of Doc (change the version number, describe the change in one line in the release history) and Publish as a single task:

<IMG  src="https://eightshapes.com/images/articles/design-system-features-step-by-step/7.png"  alt="Diagram indicating combined steps"/>

In another case where a feature — like a disabled state — is documented sufficiently by a coded example and requires no further elaboration, we’ll skip the Doc step and combine Build / Publish step.

<IMG  src="https://eightshapes.com/images/articles/design-system-features-step-by-step/8.png"  alt="Diagram indicating combined steps"/>

In any case where steps are combined into a single task, the completion criteria for all steps still apply to the task.

# Reflect the Steps in Task or Subtask Titles
Naming conventions — or lack thereof — within a backlog can reflect a level of predictability and rigor of a team.

As I’ve instituted this workflow across many teams over the past few years, our backlogs have become a scannable set of titled tasks for which we can accurately predict the outcomes, reviewers, and relationships of each one.

<IMG  src="https://eightshapes.com/images/articles/design-system-features-step-by-step/9.png"  alt="Comparison of Jira task titles, verbose and unstructured versus succinct and structured"/>

We’ll use the ticket’s title to reflect a feature’s name and workflow step, and leave the acceptance criteria and deeper descriptions to the details.


