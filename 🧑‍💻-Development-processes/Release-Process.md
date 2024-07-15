The following release process accomplishes two things - merging the current `master` branch into the `release` branch, and publishing the release branch to the NPM.

Our [branching approach](https://dev.azure.com/AB-Design/Apollo%20Design%20Systems/_wiki/wikis/Apollo-Design-Systems.wiki/30/Branching) allows for continuous development with periodic release.

## Update release with the latest master

1. Create a new branch from latest release
2. Merge latest master into the newly created branch
3. Create a new Pull Request
	- From newly created branch to ‘release’ branch
	- Title: release version (ex. 3.1.0)
	- Glimpse at task list to see what is included
	- Skim & gut check the files before hitting ‘create’
4. Click on ‘job’ in the PR Overview to watch the process
5. When ‘finished’, go check Apollo release in chromatic
	- Sanity check changes
	- Approve all changes 
6. Go back to the PR and re-queue
7. Complete the PR
	- Change `Merge type` to `Squash commit`
	- Check `Delete <branchname> after merging`
	- Check `Complete associated work items after merging`

## Publish to NPM

8. Go to Pipelines in ADO
	- Publish all packages
	- Run pipeline
        - Dropdown menu – ‘release’
		- Variables (button on top right)-> 
			- PUBLISH_VERSION -> Change release number to new release number
			- TAG_NAME -> Change to `latest`
		- Run

9. Click on ‘job’ to watch the process

10. Check the new version in the example apps to make sure the release is working as expected

10. If everything looks good, you can proceed to the [Post Release Tasks](https://dev.azure.com/AB-Design/Apollo%20Design%20System/_wiki/wikis/Apollo-Design-Systems.wiki/132/Post-Release-Tasks) to make sure our documentation is updated


