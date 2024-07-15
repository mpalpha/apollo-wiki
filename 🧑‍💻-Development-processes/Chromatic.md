Used by the Apollo team as a visual regression testing tool, [Chromatic](https://www.chromatic.com/) allows us to ensure our Components don't mistakenly change visually due to code changes.

Chromatic URLs on zeroheight point to our release branch so only production ready examples are shown using the following base URL:
[https://release--61955eff5bf6f2004a6a0b54.chromatic.com](https://release--61955eff5bf6f2004a6a0b54.chromatic.com)

If we need to run a manual build in Chromatic we can do so from a CLI using the following command:
`yarn dlx chromatic --project-token=3bbaeeb1a95c --auto-accept-changes`