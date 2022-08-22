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

The example release shows a PR merge from <kbd>dev</kbd> to <kbd>main</kbd> with
`SemVer:Major++` label applied. 
