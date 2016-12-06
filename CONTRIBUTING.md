Contributing guide
==================
This contributing guide describes the working procedure of the further development of Molsim. Changes and new features should always be implemented following the guidelines given below. The procedure can be summed up to the following steps: 

  1. [Generate a new branch](#1-how-to-generate-a-new-branch)
  2. [Commit features/changes](#2-how-to-commit-featureschanges)
  3. [Request a merge into Master](#3-how-to-request-a-merge-into-master)
  4. [Review a merge request](#4-how-to-review-a-merge-request)
  5. [Resolve all discussions](#5-how-to-resolve-all-discussions)
  6. [Merge it!](#6-how-to-merge-it)
  7. [Finalize your merge](#7-how-to-finalize-your-merge)

Most of the tasks may either be done using the [gitlab interface](https://git.rwth-aachen.de/pascal.hebbeker/Molsim/) or by using the command line. In this contributing guide the respective way is described, of which the authors think it is most convenient.

## 1. How to generate a new branch
Changes of Molsim may only be made within the scope of [branches](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging). This way you can implement your changes without messing with the main version (`master`) of Molsim. To generate a new branch:
```sh
git checkout -b <NAME-OF-NEW-BRANCH>
```
The just created branch exists only locally, to set it up on the remote repository use
```sh
git push --set-upstream origin <NAME-OF-NEW-BRANCH>
```
You're now in your new branch. You may now begin to implement new features/changes.
## 2. How to commit features/changes
The changes you apply to the code should be as efficient and non-invasive as possible. Try to divide your modifications in logically-associated chunks of code. These chunks can then individually be commited and described in a commit message. After you changed something you first have to stage the files in which changes were made and which you'd like to commit.
```sh
git add <LIST-OF-MODIFIED-FILES>
``` 
After staging one or several files you may now commit using
```sh
git commit -m "<YOUR-MESSAGE>"
```
The advantage of chopping all changes into smaller chunks of code is the option to revert individual commits. In addition it enhances the transparency of what you do and others can better follow your changes. Whenever you stop working on your branch, you should always push your commits in order to upload them.
```sh
git push
```
Whenever you start to work on your branch again you should pull the branch in order to download the current version of your branch.
```sh
git pull
```
When you're done with your modifications, you may request a merge of your branch into the `master`. Before doing so, please confer [this checklist](#appendix-checklist) and make sure, that all requirements have been satisfied.
## 3. How to request a merge into Master
In order to request a merge of your branch into the `master` browse the [gitlab interface](https://git.rwth-aachen.de/pascal.hebbeker/Molsim/merge_requests) to create a new merge request. Note to request the merge with a WIP-prefix. The merge is then designated as "work in progress".
## 4. How to review a merge request
When you are assigned to a merge request you are supposed to read the changes in the code and check for possible mistakes. Besides of possible mistakes the code should be straight forward to understand. If parts of the code are difficult to understand, request more comments! When reviewing the code differences using git (or the [gitlab interface](https://git.rwth-aachen.de/pascal.hebbeker/Molsim/merge_requests)) hide whitespace changes. Whenever you find something to be wrong or incomprehensible, add a comment to the respective line of code. This will start a discussion to be resolved by the author of the modification.

Some general rules when commenting the changes of the code:
* When reviewing the code, mark comments regarding ''cosmetic'' changes in the code with :sparkles: (`:sparkles: `).
* Mark all general comments (*i.e.* comments not related to a specific line of code) which require further attention with :negative_squared_cross_mark: (`:negative_squared_cross_mark:`).

Besides of the reviewing of the detailed code modifications, please check whether all requirements in [this checklist](#appendix-checklist) have been met. When you are finished reviewing all modifications and all discussions have been resolved, remove the WIP-prefix from the merge request. This signals the author of the modifications, that his branch may be merged.
## 5. How to resolve all discussions
When the issue of the comment was resolved, mark it with :white_check_mark: (`:white_check_mark:`)
## 6. How to merge it
## 7. How to finalize your merge
## Appendix: Checklist
* Make sure, that the [Testin](https://git.rwth-aachen.de/pascal.hebbeker/Molsim/wikis/testin) runs clean! For further informations confer the corresponding [Wiki entry](https://git.rwth-aachen.de/pascal.hebbeker/Molsim/wikis/testin).
* Ascertain, that the compilation with `mode=warn` does not trigger any warnings related to your modifications!
* Describe all changes in the [Wiki](https://git.rwth-aachen.de/pascal.hebbeker/Molsim/wikis/home)!
* Change the version number corresponding to [Semantic Versioning](http://semver.org/)!