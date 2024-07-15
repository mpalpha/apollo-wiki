# Consuming @apollo code artifacts

## Configuration for node/npm based projects

You will need to configure both your local machine and your CI pipeline to consume @apollo code artifacts as dependencies.

## Local configuration

Follow the instructions to [Connect to the feed](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_packaging?_a=connect&feed=apollo-design-system) in Azure DevOps Artifacts

### Temporary Workaround to `self signed certificate in certificate chain` error

Bypass strict ssl check:

npm
```npm config set strict-ssl=false```

yarn
```yarn config set strict-ssl=false```

You should now be able to install @apollo packages locally
`npm install @apollo/<package>`

## Usage in Azure DevOps Pipelines

### [Create a Personal Access Token](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops&tabs=preview-page#create-a-pat)
Ideally this PAT would belong to an admin account rather than a particular individual's account.

### Navigate to your Project Settings in Azure DevOps and Create a Service Connection
1. Select the New Service Connection Button ![Screen Shot 2021-08-19 at 4.23.53 PM.png](/.attachments/Screen%20Shot%202021-08-19%20at%204.23.53%20PM-32abe190-c599-4f4b-b1e8-99e7c3baa80b.png)
2. Choose an Npm connection type ![Screen Shot 2021-08-19 at 10.33.13 AM.png](/.attachments/Screen%20Shot%202021-08-19%20at%2010.33.13%20AM-1604ec2a-e241-4ff3-8d41-f37ea3cde76c.png)
3. Set the properties of the service connection:
- Authentication method: authentication token
- Registry Url: Copy and paste the url for the design system feed - https://pkgs.dev.azure.com/AB-Design/59b17b42-1fc0-42fd-89d2-2655cf83b317/_packaging/apollo-design-system/npm/registry/ 
- Authentication: Use PAT in generated above
- Give your service connection a name you can recognize e.g. apollo-npm-registry
- Grant access permission to all pipelines
- Choose Save

### Configure your Pipeline
Your CI pipeline will need to include an npm authenticate (for task runners) task

#### YML

```steps:
- task: npmAuthenticate@0
  displayName: 'npm Authenticate .npmrc'
  inputs:
    workingFile: .npmrc
    customEndpoint: 'apollo-design-system-registry'
```

#### Using the classic Azure DevOps editor
Add npm Authenticate (for task runners) 
![Screen Shot 2021-08-19 at 4.40.31 PM.png](/.attachments/Screen%20Shot%202021-08-19%20at%204.40.31%20PM-6b8cfe39-48c1-48b6-97e7-df22eb4fa832.png)

- .npmrc file to authenticate - select the project .npmrc - [see instructions for connect to feed](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_packaging?_a=connect&feed=apollo-design-system)

- Credentails for registries outside this organization/collection: select the service connection you created above

## Using components

### React

Import apollo components from the `@apollo/react-bindings` package and use the components as any other react component. Make sure to use the PascalCase of the component's name.

example:
``` 
import { AbdsButton } from '@apollo/react-bindings';
...
<AbdsButton 
    palette="brand" 
    icon-start={props.label === "Add Todo" ? 'add' : null} 
    onClick={handleClick}>
    {props.label}
</AbdsButton>

```
See [an example todo app written in React](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_git/example-app-react)
### Angular

Follow the instructions on [stencil's docs](https://stenciljs.com/docs/angular) to:
1. Include the CUSTOM_ELEMENTS_SCHEMA in the modules that use the components.
2. Call defineCustomElements() from main.ts.

Then use @apollo components in your templates as you would any other html element.
Example:

``` 
<div class="mt-2">
    <abds-button palette="brand" icon-start="add" (click)="addItem('New Todo Item')">Add Todo</abds-button>
</div>
```

See [an example todo app written in Angular](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_git/example-app-angular)