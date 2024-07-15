![Monorepo structure - Tailwind configuration(2).png](/.attachments/Monorepo%20structure%20-%20Tailwind%20configuration(2)-b77138da-9c92-4b23-9a55-d30fed209431.png =650x)

The styles package generates a `styles.css` file and a storybook static documentation site.

It is also the 'owner' of the tailwind configuration imported by other other packages: 

- Components: imports tailwind configuration in `stencil.config.ts` as a postcss plugin 
- Icons: imports tailwind configuration in `postcss.config.js` as a plugin

Run the [Tailwind Config Viewer](https://github.com/rogden/tailwind-config-viewer) to visualize the output of the Tailwind CSS configuration file.

```
cd packages/styles && npx tailwind-config-viewer -o
```