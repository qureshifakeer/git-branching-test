
1. What is a Git Branch?
A Git branch is an independent line of development. It points to a specific commit and allows developers to work on new features, bug fixes, or experiments without affecting the stable code on the main branch.
2. Why are branches important in software development?
 * Parallel Work: Multiple team members can work on different tasks simultaneously.
 * Code Safety: Incomplete or broken code stays isolated from the production branch.
 * Easy Collaboration: Teams can review and test changes via Pull Requests before merging.
3. What is the difference between git branch and git switch?
 * git branch: Used primarily to create, list, rename, or delete branches (it does not switch to the branch).
 * git switch: A modern Git command specifically designed to switch between existing branches or create and switch to a new branch using -c.
4. What is a Feature Branch Workflow?
In a Feature Branch Workflow, all new feature development happens on dedicated branches created off the main branch (e.g., feature/login). Once the feature is completed and tested, it is merged back into the main branch via a Pull Request.
5. Why are branch naming standards important?
 * Clarity: Clear names (like feature/user-auth or bugfix/cart-error) instantly explain what the branch is for.
 * Organization: Helps large teams track who is working on what without confusion.
 * Automation: CI/CD pipelines can trigger specific build and test jobs based on branch prefixes.
6. What is Git Flow?
Git Flow is a branching model designed around planned project releases. It uses multiple long-lived branches:
 * main (production code)
 * develop (integration branch)
 * Short-lived branches like feature/*, release/*, and hotfix/*.
7. What is Trunk-Based Development?
Trunk-Based Development is a branching strategy where all developers frequently merge small, short-lived branch updates directly into a single central branch (called trunk or main), usually multiple times a day.
8. What is the difference between Git Flow and Trunk-Based Development?
 * Git Flow: Relies on multiple long-lived branches (main, develop), longer development cycles, and planned releases. Merges happen less frequently.
 * Trunk-Based Development: Relies on a single shared trunk (main) with short-lived branches (1–2 days max), frequent merges, and continuous integration.
9. Which branching strategy is commonly used in modern DevOps environments?
Trunk-Based Development is the standard in modern DevOps. It supports fast CI/CD pipelines, automated testing, and frequent production deployments.
10. What is the purpose of a feature branch?
The purpose of a feature branch is to isolate changes for a specific user story, task, or feature until it is fully written, tested, reviewed, and ready to be merged into the main codebase.
11. Which command creates and switches to a new branch in a single step?
Using switch:
git switch -c <branch-name>

Or using classic checkout:
git checkout -b <branch-name>

12. Why do DevOps teams prefer Trunk-Based Development?
 * Eliminates Merge Hell: Short-lived branches prevent large, painful merge conflicts.
 * Faster CI/CD: Small commits trigger automated testing and faster feedback loops.
 * Continuous Delivery: The main branch stays continuously releasable to production.
13. What is the difference between git branch -d and git branch -D?
 * -d (Safe delete): Deletes a branch only if its changes have already been merged into the upstream branch. If unmerged changes exist, Git prevents deletion.
 * -D (Force delete): Forcefully deletes the branch regardless of its merge status, discarding all unmerged commits. Equivalent to git branch --delete --force.





1. You accidentally created a branch named featurelogn instead of feature-login. Rename it correctly.
 * Explanation: Use the git branch -m command to rename the branch.
 * Command (If you are already on that branch):
   git branch -m feature-login

 * Command (If you are on a different branch):
   git branch -m featurelogn feature-login

 * Verification: Run git branch to confirm that feature-login appears with the correct spelling.
2. A branch has already been merged into master/main. Which command should be used to safely delete it?
 * Explanation: Use the safe delete flag -d (lowercase). Git will only allow deletion if all changes have already been merged into the upstream branch.
 * Command:
   git branch -d <branch-name>

   (Example: git branch -d feature-login)
 * Verification: Run git branch to ensure the branch name no longer appears in the list.
3. How can you verify the branch you are currently working on?
 * Primary Command:
   git branch --show-current

 * Alternative Commands:
   * git branch — Displays all local branches, with an asterisk (*) and green text highlighting the active branch.
   * git status — The very first line displays On branch <branch-name>.
4. How can you display both local and remote branches?
 * Explanation: Use the git branch command with the -a (all) flag.
 * Command:
   git branch -a

 * Verification: Local branches will be listed normally, and remote-tracking branches will appear in red with the prefix remotes/origin/<branch-name>.



