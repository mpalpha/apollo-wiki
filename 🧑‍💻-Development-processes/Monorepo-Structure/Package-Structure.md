# Packages
Our monorepo consists of the following packages:
* [components](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_wiki/wikis/Apollo-Design-Systems.wiki/47/Package-Structure?anchor=user-content-%5Bcomponents%5D(https%3A%2F%2Fdev.azure.com%2Fab-design%2Fapollo%2520design%2520systems%2F_git%2Fapollo%3Fpath%3D%252fpackages%252fcomponents))
* [icons](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_wiki/wikis/Apollo-Design-Systems.wiki/47/Package-Structure?anchor=%5Bicons%5D(https%3A//dev.azure.com/ab-design/apollo%2520design%2520systems/_git/apollo%3Fpath%3D%252fpackages%252ficons))
* [styles](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_wiki/wikis/Apollo-Design-Systems.wiki/47/Package-Structure?anchor=%5Bstyles%5D(https%3A//dev.azure.com/ab-design/apollo%2520design%2520systems/_git/apollo%3Fpath%3D%252fpackages%252fstyles))

**Package file structure:**

## [components](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_git/apollo?path=%2Fpackages%2Fcomponents)
::: mermaid
graph LR
  A1[src] --> A1B1[components]
  A1 --> A1B2[assets]
  A1 --> A1B3[utils]

  A1B1 --> A1B1C1[component]

  A1B1C1 --> A1B1C1D1[stories]

  A1B1C1D1 --> A1B1C1D1E2[api.stories.mdx]
  A1B1C1D1 --> A1B1C1D1E1[variant*.stories.mdx]
  A1B1C1D1 --> A1B1C1D1E3[interactive.stories.mdx]

  A1B1C1 --> A1B1C1D2[tests]

  A1B1C1D2 --> A1B1C1D2E1[component.e2e.ts]
  A1B1C1D2 --> A1B1C1D2E2[component.spec.ts]

  A1B1C1 -- styling --> A1B1C1D3[component.css]
  A1B1C1 -- component --> A1B1C1D4[component.tsx]
  A1B1C1 -- interfaces/types --> A1B1C1D5[types.ts]

  A1B1 -- global component interfaces/types --> A1B1C2[types.ts]

  A1B2 --> A1B2C1[styles]

  A1B2C1 -- global styling --> A1B2C1D1[common.css]

  A1B3 --> A1B3C1[global utility files]
:::

## [icons](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_git/apollo?path=%2Fpackages%2Ficons)
::: mermaid
graph LR
  A1[src] -- svg icons --> A1B1[img]
  A1 --> A1B2[stories]
:::

## [styles](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_git/apollo?path=%2Fpackages%2Fstyles)
::: mermaid
graph LR
  A1[src] -- deprecated --> A1B1[components]
  A1 --> A1B2[fonts]
  A1 --> A1B3[stories]
  A1 --> A1B4[templates]
  A1 --> A1B5[global files]

  A1B5 --> A1B5C1[fonts.css]
  A1B5 --> A1B5C2[styles.css]
:::