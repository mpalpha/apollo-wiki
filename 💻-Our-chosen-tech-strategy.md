# Digital products at AmerisourceBergen

AmerisourceBergen's digital ecosystem spans a range of various business segments, comprised of different platforms/portfolios whose products leverage disparate technologies powering much of their front-end interfaces.

In the absence of a unified enterprise architecture, this is why we are pursuing custom web components that integrate agnostically with different libraries and/or frameworks. Apollo utilizes [Stencil](https://stenciljs.com/), which combines the best concepts of the most popular frameworks into a simple build-time tool.

[[_TOC_]]

---

# Stencil: A Web Components Compiler

Stencil generates standards-compliant Web Components that can work with popular frameworks right out of the box. In addition, Stencil can be used to generate framework native components that can be used just like any other components in your framework of choice. Stencil accomplishes this by wrapping your Web Components via Stencil's Output Target feature.

Compared to using Custom Elements directly, Stencil provides extra APIs that makes writing fast components simpler. APIs like Virtual DOM, JSX, and asynchronous rendering make fast, powerful components easy to create, while still maintaining 100% compatibility with Web Components. Stencil also enables a number of key capabilities on top of Web Components, in particular, prerendering, and objects-as-properties (instead of just strings).

---

# Design Systems & Component Libraries

Stencil's primary objective is providing amazing tools for design systems and component libraries. Components as a concept provide similar language for engineers and designers to have productive conversations about design implementation. Visit the Stencil for Design Systems page to learn more.

---

# Why Web Components?

Framework fragmentation has created a web development interoperability nightmare, where components built for one framework didn't work with another framework.

Web Components offered a solution to both problems, pushing more work to the browser for better performance, and targeting a standards-based component model that all frameworks could use.

Web Components by themselves, however, weren't enough. Building fast web apps required innovations that were previously locked up inside traditional web frameworks. Stencil was built to pull these features out of traditional frameworks and bring them to the fast emerging Web Component standard. While Stencil is intended to be used primarily to build design systems and component libraries, these innovations allowed entire applications to be built using only Stencil.

