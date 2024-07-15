# Approach

![Screen Shot 2021-11-19 at 9.12.34 AM.png](/.attachments/Screen%20Shot%202021-11-19%20at%209.12.34%20AM-79047388-8ae1-4843-8c4d-6cd6098204d9.png)

## Apollo's branching and merging strategy is modeled after [Trunk Based Development](https://trunkbaseddevelopment.com/) and conforms to the following conventions:
- There are two long running branches, `master` and `release`
- The default branch is named `master`.
- Features, bug fixes and other change type branches are ephemeral and made directly off of the `master` branch.
- Pull requests are required in order to merge into `master` and `release`.
- Pull requests must pass automated tests and code review. Key developers have permission to bypass these requirements in emergency situations.
- Design approval should be requested on an as needed basis
- PRs that have passed all tests and received approvals are squashed into a single commit and merged.
- If bugs are found after deploying a release branch then `bugfix` branch should be created off of `master` and a PR opened from the `bugfix` to `master`, and then on to `release`. 

# Process

## Changes to `master`

1. Create a branch off `master` and name the branch with a type and description. Branch type is either `feature`, `bugfix`, `task`, or `hotfix`
```
git checkout -b branchType/myBranchDescription
```
2. Make related changes and push commits to branch
3. Create Pull Request against `master`
a. Ensure all tests are passing and test coverage meets threshold _-WIP-_
b. Generate Chromatic snapshots and attach link to PR
c. Pass code review
d. Pass design review (if applicable)
4. Merge PR. Warning: Only the creator of the PR should merge

## Releasing - This is a WIP and will be updated 

1. Create Pull Request to merge `master` into `release`
a. Ensure all tests are passing 
b. Generate Chromatic snapshots - 
c. Pass design review 
2. Merge PR into release
3. Manually trigger the Publish all Packages pipeline (`publish-pipeline.yaml`) to publish code artifacts to registry


## Build pipelines

![Screen Shot 2021-11-18 at 3.32.42 PM.png](/.attachments/Screen%20Shot%202021-11-18%20at%203.32.42%20PM-ce5eecf7-925e-4a4d-9a72-b6f74826a0ad.png)

1. PR Merge (`test-pipeline.yaml`) runs as branch policy on PR's against `master`.  The build will fail on unaccepted visual changes in chromatic.  Resolve visual diffs and run the pipeline manually.

2. Chromatic Publish (`chromatic-pipeline.yaml`) runs when changes are merged to master. The build will fail on unaccepted visual changes in chromatic.  In the rare case that this happens, look for unexpected changes resulting from the merge to master.

3. PR Merge (`test-pipeline.yaml`) runs as branch policy on `release` branch.  The build will fail on unaccepted visual changes in chromatic, which is almost guaranteed.  The scope of the diffs will reflect all changes since the last release.  Design must sign off on these changes.  Resolve visual diffs and run the pipeline manually.

4. Publish all Packages (`publish-pipeline.yaml`) is run manually on release.  Will fail (unexpectedly) on unaccepted visual changes in chromatic.

For more on build pipelines, see the [Build Pipelines](/Development/Build-Pipelines) documentation