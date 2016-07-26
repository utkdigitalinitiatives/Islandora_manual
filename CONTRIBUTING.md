# Welcome!

If you are reading this document then you are interested in contributing to the Islandora Manual. All contributions are welcome!

## Workflows

Please follow the file structure format.To read more on Gitbook structure please read [GitBook Toolchain Documentation: Directory Structure](http://toolchain.gitbook.com/structure.html)

| File / Folders | Description                                                   |
|----------------|---------------------------------------------------------------|
| book.json      | Stores configuration data (optional)                          |
| README.md      | Preface / Introduction for your book (required)               |
| SUMMARY.md     | Table of Contents (See Pages) (optional)                      |
| GLOSSARY.md    | Lexicon / List of terms to annotate (See Glossary) (optional) |
| repositories/  | Configuration scripts and repos                               |
| modules/       | Islandora or Drupal Repositories                              |
| basics/        | Simple tasks like installs or ingests                         |
| images/        | Locally hosted images/illustrations                           |

### Use cases

If you would like to submit a use case for this project, please submit and issue [here](https://github.com/utkdigitalinitiatives/Islandora_manual/issues) using the [Use Case template], assign the "use case" label to the issue.

### Documentation

You can contribute documentation in two different ways. One way is to create an issue [here](https://github.com/utkdigitalinitiatives/Islandora_manual/issues) assign the "documentation" label to the issue. Another way is to by pull request, as same as code contribution.

### Request a new feature

To request a new items you should [open an issue](https://github.com/utkdigitalinitiatives/Islandora_manual/issues) or create a [use case](https://github.com/Islandora/Islandora-Fedora4-Interest-Group/issues) (see _use case_ section above), and summarize the desired functionality. Select the label "enhancement" if creating an issue on the project repo, and "use case" if creating a use case in the interest group repo.

### Report a corrections

To report a correction you should [open an issue](https://github.com/utkdigitalinitiatives/Islandora_manual/issues) that summarizes the correction. Set the label to "correction".

In order to help us understand and make the correction it would be great if you could provide us with:

1. The correct steps to reproduce the issue with the instructions. This includes information about e.g. the Islandora version you were using along with version of stack components.
2. The expected behavior.
3. The actual, incorrect behavior.

Feel free to search the issue queue for existing issues (aka tickets) that already describe the problem; if there is such a ticket please add your information as a comment.

**If you want to provide a pull along with your bug report:**

That is great! In this case please send us a pull request as described in section _Create a pull request_ below.

### Contribute code

If you are contributing Drupal code, it must adhere to [Drupal Coding Standards](https://www.drupal.org/coding-standards); Gitbook will check for this on pull requests.

Contributions to the Islandora Manual codebase should be sent as GitHub pull requests. See section _Create a pull request_ below for details. If there is any problem with the pull request we can work through it using the commenting features of GitHub.

* For _small patches_, feel free to submit pull requests directly for those patches.
* For _larger code contributions_, please use the following process. The idea behind this process is to prevent any wasted work and catch design issues early on.

    1. [Open an issue](https://github.com/utkdigitalinitiatives/Islandora_manual/issues) and assign it the label of "enhancement", if a similar issue does not exist already. If a similar issue does exist, then you may consider participating in the work on the existing issue.
    2. Comment on the issue with your plan for implementing the issue. Explain what pieces of the codebase you are going to touch and how everything is going to fit together.
    3. Our developers will work with you on the design to make sure you are on the right track.
    4. Implement your issue, create a pull request (see below), and iterate from there.

### Create a pull request

Take a look at [Creating a pull request](https://help.github.com/articles/creating-a-pull-request).  In a nutshell you
need to:

1. [Fork](https://help.github.com/articles/fork-a-repo) the Islandora Manual GitHub repository at [https://github.com/utkdigitalinitiatives/Islandora_manual](https://github.com/utkdigitalinitiatives/Islandora_manual) to your personal GitHub account. If you already have a fork of [https://github.com/utkdigitalinitiatives/Islandora_manual](https://github.com/utkdigitalinitiatives/Islandora_manual) Github will prevent you from creating a new fork; in such a case you can continue to use [https://github.com/utkdigitalinitiatives/Islandora_manual](https://github.com/utkdigitalinitiatives/Islandora_manual) to issue pull request, be cautious of which branches you work from though (you'll want to base your work off of master). Also be cautious of which repository your issuing your Pull Request to (you'll want to issue your pull request to [https://github.com/utkdigitalinitiatives/Islandora_manual](https://github.com/utkdigitalinitiatives/Islandora_manual)). See [Fork a repo](https://help.github.com/articles/fork-a-repo) for detailed instructions.
2. Commit any changes to your fork.
3. Send a [pull request](https://help.github.com/articles/creating-a-pull-request) to the Islandora GitHub repository that you forked in step 1.  If your pull request is related to an existing issue -- for instance, because you reported a [bug/issue](https://github.com/utkdigitalinitiatives/Islandora_manual/issues) earlier -- prefix the title of your pull request with the corresponding issue number (e.g. `issue-123: ...`). Please also include a reference to the issue in the description of the pull. This can be done by using '#' plus the issue number like so '#123', also try to pick an appropriate name for the branch in which you're issuing the pull request from. 

You may want to read [Syncing a fork](https://help.github.com/articles/syncing-a-fork) for instructions on how to keep your fork up to date with the latest changes of the upstream (official) `islandora` repository.
