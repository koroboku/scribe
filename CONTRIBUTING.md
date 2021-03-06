# Contributing

These steps also apply to plugins.

* Add a failing test
* Create isolated cases for browser inconsistencies (see https://github.com/guardian/scribe/blob/master/BROWSERINCONSISTENCIES.md)
* No assumptions should be made in the code – comment every little detail with
  references to isolated cases (when dealing with browser inconsistencies)

## Testing Locally
Please see the [wiki](https://github.com/guardian/scribe/wiki/Testing) for details of how to run the scribe test suite.


## Releasing

### Bower
* `git checkout master`
* Run `./release.sh [ <newversion> | major | minor | patch | build ]` (we use
  [mversion](https://github.com/mikaelbr/mversion#usage-cli)). (If releasing a
  plugin, run the script inside this repository from the plugin’s directory.)
* Checkout the `dist` branch to check you're happy with the compilation result.
  If you are, run `git push; git push --tags`. (The `dist` tree is for
  distribution via Bower).

### npm
* `git checkout master`.
* Update `CHANGELOG.md`
* Update the version number in `package.json`
* Commit with message of `v<number>`
* `git push`
* Run `npm publish`

### Update example
* `git checkout gh-pages`
* `git pull`
* Update necessary dependency versions in `bower.json`. Check `bower ls` to see
  which components need updating.
* `bower install`
* `bower prune`
* `git add --update .` (don't include untracked files from source Bower
  components)
* Commit using version number as the message (OR plugin version)
* `git push`

## Conventions
* In documentation and code, refer to nodes by their canonical node name in
  uppercase. E.g. `P`.
* When creating variables that refer to nodes or elements, suffix them with
  `node` or `element` respectively. E.g. `pElement` or `textNode`.

## Tools
* Paste bin: http://jsfiddle.net/OliverJAsh/z8FTb/
