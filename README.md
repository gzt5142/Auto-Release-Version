# Auto-Release-Version

Example GitHub action configuration to manage releases and SemVer strings. 

----

The example action in `./github/workflows/release-on-pr-merge-to-main.yml` will fire 
when a pull request closes with a merge to the <kbd>main</kbd> branch. 

Upon such a PR/merge: 

* The [SemVer](https://semver.org/) is incremented, and a git tag is assigned. 
* SemVer increment is influenced by GitHub labels attached to the PR
  * If `SemVer:Major++` label is found, increments Major number 
  * If `SemVer:Minor++` label, increments minor
  * If neither found, increment patch number
* A sanitized version of the repo is zipped up and associated as a release asset. 

The example [release](https://github.com/gzt5142/Auto-Release-Version/releases/tag/v1.0.0)
shows a PR merge from <kbd>dev</kbd> to <kbd>main</kbd> with `SemVer:Major++` label applied. 

The version number is not tracked in the repo files.  Its state is maintained via
the medium of the git tags assigned to the main branch. SemVer tag strings are constructed
with 'v' plus major, minor, and patch numbers (integers between 0 and 99). 

