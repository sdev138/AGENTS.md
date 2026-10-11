# AGENTS.md

Remember to use Judgement when necessary

## Say my name before you respond

First things first. Before any message, you must say the name of the user, Samarth, as the first thing, then start the message. As an example:
"Samarth, here is a list of goals of what needs to be done."

## 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:

* State your assumptions explicitly. If uncertain, ask.
* If multiple interpretations exist, present them - don't pick silently.
* If a simpler approach exists, say so. Push back when warranted.
* If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

* No features beyond what was asked.
* No abstractions for single-use code.
* No "flexibility" or "configurability" that wasn't requested.
* No error handling for impossible scenarios.
* If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:

* Don't "improve" adjacent code, comments, or formatting.
* Don't refactor things that aren't broken.
* Match existing style, even if you'd do it differently.
* If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:

* Remove imports/variables/functions that YOUR changes made unused.
* Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:

* "Add validation" → "Write tests for invalid inputs, then make them pass"
* "Fix the bug" → "Write a test that reproduces it, then make it pass"
* "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:

```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.

## 5. General Guidelines

* Always use the brainstorming and autoprompt skill before starting any task, as these skills is relevant to all workflows
* Always use consise and simple technical language, without leaving any context
* If a workspace does not have a MEMORY.md file, make sure to create a MEMORY.md file and log information into the file however you see fit, for future rules and usage about this file go ot the "Additional Rules that must be followed" section (which is the next section after this line)

## 6. Making changes in a coding project

* When making commits to the project, you need to do the following, ensure that you are not making changes to the "main"/"master" branches. Make sure you checkout and create and switch to another branch to write your changes. If the changes are done in a separate branch already, you would still need to take your changes to another branch. For example, if the changes are already on a branch called "feature/AI-3", then your changes need to be on "feature/AI-3-<agent-name>-\<3-word-summary-of-feature>" and if the current branch is on "main" or "master", then your new branch needs to be called "\<3-word-summary-of-feature>-<agent-name>"
* As you can already tell, the standard naming conventions for naming a branch is the following: "<branch/feature-name>-<agent-name>-\<3-word-summary-of-feature>". Ideally you would work on a single branch (with a single change number), but their are cases where I may ask you to create another branch to compare changes side-by-side, or if you deem it necessary, where the code becomes so convoluted that a new branch is necessary. But if you do create another branch, make sure you delete the old branch that you were working on.
* When you make changes, you must always commit your changes to the branch you have created, do not merge the changes into the main/master unless it is specified in the AGENTS.md file of the project or if otherwise said

## Merging your changes

* Their will be multiple people and agents working within the codebase at the same time. Everyone will be working on their own branches at some point and so its better to coordinate and merge your changes to increase development velocity
* Remember, you CANNOT merge your changes to "main" and "master", the single person responsible for merging changes to those branches will always be the service/code owner
* Always merge your changes to the original feature branch. For instance, the original feature branch will always be the branch you forked from. For instance, if the starting branch is "feature/AI-1", and you are working on "feature/AI-1-agent-creating-homepage", then you will always merge your changes to the branch "feature/AI-1"
* Their will inevitably be merge conflicts, when merging your changes to the branch, always make sure to that you do not erase the changes that others have made. Make sure to follow these rules when addressing merge conflicts:
  * Always look at the changes that are conflicting **carefully**
  * **Identify the goal the team is trying to solve and define that said goal before looking at the merge conflicts**
  * If these changes are in certain design/spec files, identify which changes are inherently **better** and that can accomplish the specific goal that the team/you are trying to solve
  * If the changes are code related changes, identify what the other person was trying to solve, and identify what the code was trying to solve. Ensure that your new solution/merge accommodates the changes and features that were already merged prior to you trying to merge your code changes
* Once your code has been successfully merged to the original branch, make sure that you delete your branch that you worked on (the branch that you forked/created)

#### To recap, the git workflow is the following:
[Check which branch you are on] --> [Create another branch] --> [Make your edits on that branch you just switched to] --> [Commit your changes to that branch] --> [Merge your changes to the branch you switched from] --> [Check for merge conflicts] --> [Resolve merge conflicts if needed]


### Important things to note:

* You do not always have to checkout to a new branch, if you are just updating your memory file, you can do that in the current branch. The only time you need to checkout to another branch is when you HAVE to make changes to the code, remember you don't always have to do this. If you are answering questions from the user, then answer the users question, you don't need to create another git branch.

## Additional Rules that must be followed (Every single one of these rules are non-negotiable)

* When testing applications, always test locally unless otherwise said, do NOT create a playground in another proprietory environment and run your experiements their. If you can't or do not want to test locally, ask the user for permission and where to test the application. This is not negotiable.
* If you are running a local server to test an application,  ensure that you close the server once done
* If a MEMORY.md file exists in whatever workspace you are working on, then make you do the following:
  * Log the information however you would like
  * Always make sure to put the date and a separator to separate between the logs
  * Always make sure that you are adding the log to the beginning of the document
  * When you retrieve information from Memory, you dont' have to parse the entire document, just the important parts to which you need, often the most important contents are on top (due to recency bias), if you really need to then parse the entire MEMORY.md file to find and utilize all of the relevant information you are looking for.

***
