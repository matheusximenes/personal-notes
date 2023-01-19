# Github Best Practices

## Types of Commits:
* fix: fixes a bug in Uno.
* feat: new functionality to Uno.
* docs: adds or improves documentation.
* test: adds unit tests.
* perf: performance, without functional changes.
* chore: a catch-all type for any other commits. 
For instance, if you're implementing a single feature and it makes sense to divide the work into multiple commits, you should mark one commit as feat and the rest as chore.

<type>([optional scope]): <description>
E.g.: `fix(webview): Fixed video display in WebView on Android: the control was forced to use software rendering.`

    *** Note: Bug Fix it quickly
    *** Note 2: WIP - Work in Progress 


##  Branch naming conventions:
  * user unique ID's (Jira tickets numbers)
  * By adding a separator ("_" or "-"), you make the Git branch name readable
  Nono's:
  * Avoid log descriptive names
  * Avoid using only number


##  Best Practices:
1. keep it small:
    * Write the smallest amount of code possible to solve a problem
2. Atomic Commits"
    * single unit of work, involving only one task or one fix
3. Always create a brach, not commit on main or master
4. Descriptive commit messages, e.g.:  e.g. “make foo do bar"
5. Use code reviews always
6. Use a solid branch strategy (Centralized workflow / Feature branching / GitFlow / Personal branching)


##  References:
* Best Practices Github: https://about.gitlab.com/topics/version-control/version-control-best-practices/
* Commits: https://platform.uno/docs/articles/uno-development/git-conventional-commits.html
* Branch Strategies: https://www.flagship.io/git-branching-strategies/#:~:text=A%20branching%20strategy%2C%20therefore%2C%20is,interact%20with%20a%20shared%20codebase.