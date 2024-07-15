
## Build pipelines

![Screen Shot 2021-11-18 at 3.32.42 PM.png](/.attachments/Screen%20Shot%202021-11-18%20at%203.32.42%20PM-ce5eecf7-925e-4a4d-9a72-b6f74826a0ad.png)

1. PR Merge (`test-pipeline.yaml`) Runs the build and test scripts for the workspaces.  Sets the chromatic project token based on the target branch (**System.PullRequest.TargetBranch**) of the pull request (`master`, `release`) and publishes to the appropriate project.  Runs when a PR is opened against master or the release branches.
`CHROMATIC_PROJECT_TOKEN_MASTER`: chromatic project token for the **jasonlusk/Apollo** chromatic project
`CHROMATIC_PROJECT_TOKEN_RELEASE`: chromatic project token for the **jasonlusk/Apollo Release** chromatic project

2. Chromatic Publish (`chromatic-pipeline.yaml`) Runs the build and test scripts for the workspaces.  Publishes to the **jasonlusk/Apollo** chromatic project.  Runs when code is merged into the `master` branch.
variables:
`CHROMATIC_PROJECT_TOKEN_MASTER`: chromatic project token for the **jasonlusk/Apollo** chromatic project

3. Publish all Packages (`publish-pipeline.yaml`) 
 Bumps version of packages to the version set in the `PUBLISH_VERSION` variable.  Updates local dependencies to new versions and runs build and test scripts for the workspaces.  Publishes artifacts to npm registry and finally publishes storybook to the **jasonlusk/Apollo Release** chromatic project.
Run manually.
variables:
`PUBLISH_VERSION`: New version for code artifacts.  Set manually; must be semver and greater than the version currently in the registry.
`NPM_TOKEN`: Access token to npm registry.  Must belong to a team member of the `@abds` organization
`CHROMATIC_PROJECT_TOKEN_RELEASE`: chromatic project token for the **jasonlusk/Apollo Release** chromatic project


