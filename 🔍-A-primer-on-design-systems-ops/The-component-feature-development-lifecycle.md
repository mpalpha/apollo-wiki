The goal of this process is to make it easy to submit new designs (including documentation), propose changes to existing designs, and translate component designs into built components.

Before we get to more about how to integrate new components or amend existing ones, let's first cover the general structure of feature development in our design system.

The component development lifecycle has the following five stages:

<IMG  src="https://eightshapes.com/images/articles/design-system-features-step-by-step/masthead.png"  alt="Masthead"/>

[[_TOC_]]

# Discovery
Discovery clarifies the potential and the relevance of a new feature and decides whether to pursue it.

_**Assigned To:**_ Anyone on the team, although usually a designer, front-end developer or product manager.

_**Activities:**_ Triaging requests, interviews, products and system analysis, discussions with influential partners in the community, and even formal proposal processes like a contributor’s Request for Comment.

_**Definition of Done:**_
- As a system team, we understand the scope and cost of making this feature and who may do each step.
- As a system team (or product manager), we’ve (or I’ve) agreed or declined to or pursue this feature and prioritized it in our backlog.

# Design
Design finalizes a range of variations, states, and other dimensions at high fidelity so that Code can be completed, whether for visual style (e.g., new icons!), UI components (like a button), or documentation displays (like a Color page’s swatches).

_**Assigned To:**_ A designer.

_**Activities:**_ Iterative design work and critique.

_**Tools:**_ We employ Figma for all design and design systems work at AmerisourceBergen.

_**Definition of Done:**_

- As a design director (or similar role), I’ve approved the final design.
- As system designer(s) and in the community, we’ve agreed that the design solves the problem and is suitable for use across products.
- As the assigned system engineer, I have the sufficient level of variations, states, and other details to complete a build.

# Code
Code results in the codification of HTML, CSS, JavaScript, and other code.

_**Assigned To:**_ Usually a front-end developer, although at times a designer.

_**Activities:**_ Front end development and testing, often in the context of a “kitchen sink” pages (not documentation site pages) that demonstrates the range of the feature’s capabilities isolated from other system concerns.

_**Tools:**_ Code and assets, git to manage within prescribed branches, and pull requests to comment and task corrections.

_**Definition of Done:**_ To merge the feature into a release…

- As the assigned system designer, I’ve reviewed the build’s quality and confirmed it properly implemented scoped features.
- As a peer system engineer (or QA specialist), I’ve reviewed that the build functions properly, meets all quality criteria (accessibility, browser support, etc.), and adheres to system’s code styles and conventions.

# Document
To our teams, documentation is different, focused on communicating not what to build, but instead what’s built and how to use it. Doc is a separate task so that our authors focus on the quality and depth that system users crave.

_**Assigned To:**_ The designer and/or front-end developer doing the work.

_**Activities:**_
- Author documentation copy for topics like Use When, Behaviors, Editorial, and other guidelines relevant to the feature, and its variations.
- Identify if not create final code/example demonstrations.
- Compose illustrations, interactive demos, and screenshots.

_**Tools:**_ Composed on Microsoft OneNote, NOT Pull Requests! This collaboration includes a designer, engineer, reviewer(s), and ideally a technical editor too. Pull requests are primitive, limiting comments to lines.

_**Definition of Done:**_

- As a system user, I’ll have sufficient design guidance (use when, behaviors, visual style, content, & more) and code specs (reference tables, variables, code/example demos) to use the feature correctly.
- As a systems technical editor, the documentation reflects the content models and editorial standards for our documentation.

# Publish
Once documentation is complete, it must be migrated to the publishing platform for release.

_**Assigned To:**_ Front-end developer or designer capable of working in code.

_**Tools:**_ We utilize ZeroHeight to document all published design system features.

_**Activities:**_

- Migrating copy from Microsoft OneNote to the publishing platform (ZeroHeight).
- Uploading assets like images, design templates, and interactive demos.
- Finalizing live code/example demos.
- Testing page display, links, and other publishing QA.

_**Tools:**_ Usually an assortment of assets that weave into a system’s site experience, the rubber meets the road with the composed and published page(s), achieved via however content is managed.

_**Definition of Done:**_

- As a system team collaborator, I’ve reviewed committed page changes and tested page displays and links.
- As a system user, I have access to in-depth documentation of a complete feature I can use.