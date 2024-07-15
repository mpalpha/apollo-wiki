For this project we are using semantic versioning. Please see [npm documentation](https://docs.npmjs.com/about-semantic-versioning) for more details

# Release
| Code status | Stage | Rule | Example version |
|--|--|--|--|
|First release | New product|Start with 1.0.0| 1.0.0|
|Backward compatible bug fixes|Patch release|Increment the third digit|1.0.1|
|Backward compatible new features|Minor release|Increment the middle digit and reset last digit to zero|1.1.0|
|Changes that break backward compatibility|Major release|Increment the first digit and reset middle and last digits to zero|2.0.0|

# Release Candidate (RC)

Similar logic to the release versioning above. In addition to the version name, we add `-rc.x` to the end of the version, `x` being a higher version than the latest rc. Example:

- Current production version: `3.1.5`
- New rc tag would be: `3.2.0-rc.1` if we are about to do a minor version release 