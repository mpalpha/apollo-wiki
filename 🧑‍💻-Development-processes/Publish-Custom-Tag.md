Please [see wiki](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_wiki/wikis/Apollo-Design-Systems.wiki/106/Version-Naming-Convention) for more information about version naming convention for this project

# Steps
1. Navigate to the ["Publish all packages" pipeline](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_build?definitionId=21)
2. Click "Run pipeline" button in the upper right
3. Select the source branch for your tag, for this example we will use "master", please see _Figure 1_
-_Note: Yes, this means you don't have to merge your code into master to create a custom tag_
4. Under "Advanced options", click "Variables"
5. Modify `TAG_NAME` to `rc` 
6. Modify `PUBLISH_VERSION` to a compliant version
7. Navigate back to the `Run pipeline` overlay
7. Click "Run" button in the lower right

_Figure 1:_

![image.png](/.attachments/image-9fd4a203-fb22-46ac-88d7-87bf24c467d1.png)

# Test published version
After the pipeline run finishes successfully you can go to the respective npm registry link and click "Versions" tab.

- [Abds Components](https://www.npmjs.com/package/@abds/components)
- [Abds Icons](https://www.npmjs.com/package/@abds/icons)
- [Abds React Bindings](https://www.npmjs.com/package/@abds/react-bindings)
- [Abds Styles](https://www.npmjs.com/package/@abds/styles)

You can also go into an example app you would like to test and change the abds dependency:
- in project's `package.json` file
  - React: `"@abds/react-bindings": "rc"`
  - Angular: `"@abds/components": "rc"`
  - JS: `"@abds/components": "rc"`

# Notes
- When installing custom tags you can either enter the exact tag name you just created, or use the tag name to install the latest of that tag like we did with `rc` in this example
- When doing a release, the `TAG_NAME` should be `latest`
- As our application grows, we might want to add more custom tags like `beta`, `next` or `experimental`
