# Commit message syntax

When tracking down problems, just looking at the code history, when trying to pinpoint the difference
between two branches/tags/releases or for automatic changelog generation proper and "good" commit messages are important
and can be a blessing.

Therefore we use the following conventions for commit messages for all ogon projects.

**Syntax**:

A commit message consists of a **header**, **body** and **footer**.

```
<header>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

## Header
The header is the first line and should in the following format:

```
<type> [<scope>]: <description>
```
Ideally the complete header is <= 72 characters. The description should use the imperative present tense (like: "add" and not "added" or "adds") and should also not end with a dot ('.').

**Type**

Type can be one of the following and describes the type of the change:

* build - any build system related change
* chore - necessary (routine) tasks or modifications that do not have any functional change (and don't match any of the other categories)
* doc - updates or changes to documentation
* fix - fix a issue, problem or something that wasn't supposed to behave like before the fix
* new - add something new, like new functionality
* perf - changes that enhance performance
* pkg - packaging related change
* style - (re-)formatting, code style fixes, etc; important: no code change
* refactor - restructure code without changing the behavior - e.g code clean ups - everything that isn't a "fix" or a "feat"
* test - any work related on tests - non testing could shouldn't be touched
* ci - all ci related changes

There are other ("special") types that a commit messages can contain:

* revert - represents a special type that should be used if a commit is reverted. In the case of revert the description should be the header of the reverted commit. The Body needs to contain the SHA of the commit that is reverted. For example: 
```
revert: fix rdp-server: explicitly link against openssl

Reverts commit:  71cf2f43776c8fb6f9ea6f8a79376920185ef875
```
* "Merge .." - identifies a merge (e.g. when a pull request was merged)
* release - identifies commit related changes

The type shouldn't be capitalized (with the exception of Merge).

**Scope**

The scope that depends on the repository you are contributing to.
It basically describes a functional component.

For example if you contribute to core possible scopes are:

* session-manager
* rdp-server
* backend-launcher
* snmon
* protocols
* backend
* misc
* utils

For details on the scopes see doc/SCOPES.md in the repository you are contributing to.

## Body

The body is a free form multi-line text that should be wrapped at a length of 72 characters.
Like the header the body should be written in imperative present tense and should contain at least the following:

* a meaningful message
* a description of problem that is addressed (what's wrong with the current code)
* how the problem was solved an why it was done this way
* in case of performance improvements measurements before and after the change for comparison
* (what other solutions were discussed/possible)

For small commits, or commits which do not need further description the body can be omitted. Examples for this are
style changes, typo fixes.

## Footer

The footer is optional. As the body it should be wrapped at a length of 72 characters.
It can be used to reference issues on GitHub that this commit closes like
```
fixes ogon-project/ogon-project#76
```
or
```
closes ogon-project/ogon-project#76
```
Multiple issues can be referenced at once see "[closing issues using keyword](https://help.github.com/articles/closing-issues-using-keywords/)" for details.

If any changes are introduced that can "break" something, add or remove new configuration settings, add or update dependencies or require additional manual steps this should be noted in the footer like:
```
BREAKS: foo bar faz
```
or
```
CONFIG: remove obsolete option xyz
```
or
```
DEPENDENCY: require latest version (xyz) of abcde
```

If the commit requires a certain version specific version of another ogon project (like if you work on a big new feature that affects multiple repositories) reference the commit required for example like:
```
REQUIRES: ogon-project/ogon@abcdefghijklmnopqrstuvwxyz
```


