# How to contribute to the ogon project

First and foremost **thank you** for your contribution \o/. 
Without you and the other volunteers these projects wouldn't be possible.

You want to get involved? Get started by reporting a bug, suggesting enhancements or new features,
contribute code or if you just want to get in touch with us join the [irc channel][support-page-irc].

Below you'll find some notes and guidelines for contributing to any component of the ogon project.
The project's repositories are hosted in the ogon-project GitHub organization.
These guidelines are best practices and choices made during the development and are not written in
stone, use them on your sole discretion. Also feel free to suggest changes - simply create a pull
request with this modified document.

If anything isn't clear or if you have further questions don't hesitate to ask
us (see [SUPPORT.md][support-page]).

## Report a BUG

Found a bug? - We would like to help you and smash the bug away.
We use a single GitHub based [issue tracker][ogon-issue-tracker] for all components/parts of the ogon-project.

**Before reporting** a bug have a look into the very same [issue tracker][ogon-issue-tracker] to see if the bug was already reported and if you can add some additional information.

If it's a **new bug** - [create a new issue][ogon-issue-new].
To save time and help us identifying the issue, a bug report should at least contain the following:

* an useful description of the bug - "It's not working" isn't good enough - you must try harder ;)
* the steps to reproduce the bug
* if applicable, the command line or the parameters you have used
* what did you expect to happen?
* what actually happened?
* version(s) used
* Linux distribution and architecture e.g. amd64, Debian
* if you built it yourself add some notes which branch you have used, also your build parameters can help
* extra information helping us to find the bug

**Thank you for reporting a bug!**


## Suggest an enhancement or new features

Another simple way to contribute is to suggest enhancements or new features. 

Before you get started and create the issue, check our [issue tracker][ogon-issue-tracker] if the feature or enhancement wasn't
already suggested. Features are labeled ["feature"][ogon-issue-search-feature] and enhancements ["enhancement"][ogon-issue-search-enhancement].
In case you want to work on the feature/enhancement yourself (yay - two thumbs UP!) continue reading
and get acquainted with our development process.


## Code contributions

For all ogon project repositories we use a [pull request based workflow](https://guides.github.com/introduction/flow/).
If you never used git or worked with GitHub before there is a lot of good documentation out there.
For example the [guides on GitHub](https://guides.github.com/).


To create a pull request the following steps are necessary:

1. [fork the repository](https://help.github.com/articles/fork-a-repo/)
2. [clone your repository on your workstation](https://help.github.com/articles/cloning-a-repository/)
3. create a local branch and start working on your modification
4. [push the created branch](https://help.github.com/articles/pushing-to-a-remote/)
5. [create the pull request](https://help.github.com/articles/creating-a-pull-request-from-a-fork/) against the main repository

If this is the first time you contribute to any ogon project repository we need you to sign the contributor license agreement (CLA). Have a look to the [CLA signing documentation][cla-sign] for the how and why and also for further information.

Once the pull request is created it will be tested, reviewed and merged if it meets all criteria (see commit and pull request guidelines).


### Commit and pull request guidelines

During development we've established some guidelines that should be taken into account when creating commits and pull request. 

* use the projects [coding conventions][coding-style]
* commit messages should be in the format as described in [commit message syntax][commit-message-syntax]
* for repositories with tests: all tests should pass  - some of them are possibly run automated when the pull request is created
* create **clean change sets**:
  * commits should be atomic (each commit should work on it's own)
  * each commit should compile
	* focus on one subject (feature/fix/..) and don't change anything else
	* do not mix functional and style changes
	* try not to mix refactorings with functional changes
* if there are ongoing reviews: try not to change the branch - if you need to do changes create fixup commits and clean up the branch once the reviews finished
* create tests and documentation for new features and enhancements
* reference fixed issues in the footer of the commit message (see  [commit message syntax][commit-message-syntax])
* if a commit or pull request of a different ogon project repository is required to use or run a commit or pull request, reference it in the footer of the commit message (see [commit message syntax][commit-message-syntax])


# Issue and pull request lables

In the following, you find a list of issue and pull request lables we use. To see all of the issues
from a label just click on the name.

## Types and states

| Label name (and search link) | Description |
| --- | --- |
| [`beginner`][issue-search-beginner] | Easier issues that are good as first issues to work on for people that want to contribute. |
| [`bug`][issue-search-bug] | Confirmed bugs. |
| [`duplicate`][issue-search-duplicate] | This issue is a duplicate of another issue that was reported before |
| [`enhancement`][issue-search-enhancement] | Request to enhance, improve or change already present functionality. |
| [`feature`][issue-search-feature] | Feature request. |
| [`invalid`][issue-search-invalid] | Invalid issues like configuration errors, wrong usage,.. |
| [`help-wanted`][issue-search-help] | Issues where we would appreciate help from the community. |
| [`waiting-for-feedback`][issue-search-wf] | Waiting for feedback of the reporter or any other participant in the issue. |
| [`wontfix`][issue-search-wontfix] | The reported issue will not be fixed (now). |

## Components

| Label name (and search link) | Description |
| --- | --- |
| [`session-manager`][issue-search-sman] | session manager |
| [`rdp-server`][issue-search-rdp] | RDP frontend related issues |
| [`core`][issue-search-core] | ogon core  |
| [`backend:x11`][issue-search-backendx11] | x11 backend (xserver) |
| [`backend:qt`][issue-search-backendqt] | Qt platform for ogon |
| [`backend:weston`][issue-search-backendweston] | weston backend |
| [`channel:rdpdr`][issue-search-rdpdr] | RDP rdpdr channel |
| [`channel:sound`][issue-search-sound] | RDP sound channel |
| [`channel:clipboard`][issue-search-clipboard] | RDP clipboard channel |
| [`greeter:qt`][issue-search-greeter] | Qt greeter |
| [`apps`][issue-search-apps] | Applications like ogon-shadow or ogon-message |


## Pull request labels

|Label name (and search link) | Description |
| --- | --- |
| [`wip`][issue-search-wip] | The pull request is work in progress and open for discussion. Changes can be expected. |
| [`review-pending`][issue-search-rp] | There are ongoing reviews. |
| [`review-required`][issue-search-rr] | Review is required. |
| [`changes-required`][issue-search-cr] | The pull request was reviews but changes are required. |
| [`cla-needed`][issue-search-cla] | One or more commits in the pull request haven an author that hasn't signed the CLA. |

[support-page-irc]: https://github.com/ogon-project/ogon-project/blob/master/SUPPORT.md#irc
[support-page]: https://github.com/ogon-project/ogon-project/blob/master/SUPPORT.md
[ogon-issue-tracker]: https://github.com/ogon-project/ogon-project/issues
[ogon-issue-new]: https://github.com/ogon-project/ogon-project/issues/new
[coding-style]: https://github.com/ogon-project/ogon-project/coding_style.md
[cla-sign]: https://www.thincast.com/en/cla
[commit-message-syntax]: https://github.com/ogon-project/ogon-project/git-commit-msg.md
[ogon-issue-search-feature]: https://github.com/ogon-project/ogon-project/labels/feature
[ogon-issue-search-enhancement]: https://github.com/ogon-project/ogon-project/labels/enhancement
[issue-search-core]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Acore
[issue-search-rdp]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Ardp-server
[issue-search-sman]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Asession-manager
[issue-search-backendx11]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Abackend%3Ax11
[issue-search-backendqt]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Abackend%3Aqt
[issue-search-backendweston]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Abackend%3Aweston
[issue-search-rdpdr]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Achannel%3Ardpdr
[issue-search-sound]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Achannel%3Asound
[issue-search-clipboard]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Achannel%3Aclipboard
[issue-search-greeter]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Agreeter%3Aqt
[issue-search-apps]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Aapps
[issue-search-wip]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Awip
[issue-search-rp]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Areview-pending
[issue-search-rr]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Areview-required
[issue-search-cr]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Achanges-required
[issue-search-cla]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Acla-needed
[issue-search-bug]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Abug
[issue-search-enhancement]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Aenhancement
[issue-search-feature]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Afeature
[issue-search-beginner]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Abeginner
[issue-search-duplicate]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Aduplicate
[issue-search-invalid]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Ainvalid
[issue-search-help]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Ahelp-wanted
[issue-search-wf]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Awaiting-for-feedback
[issue-search-wontfix]: https://github.com/ogon-project/ogon-project/issues?q=is%3Aopen+label%3Awontfix
