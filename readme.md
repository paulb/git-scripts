# Helper scripts for git actions

## git-create-branch

- Creates a new branch or checks out an existing remote branch
- Switches to the new branch

Usage: `git-cbranch feature/thing-1`

## git-delete-branch

- Deletes a branch from both local and remote
- Will not delete the local branch if you are on it
  - If you provide a second branch name, it will switch to that branch
    then delete the branch named by the first argument

Usage:

- when on a different branch (e.g., `main`)
  `git-dbranch feature/thing-1`
- when on a the branch you wish to delete (switches to `main`)
  `git-dbranch feature/thing-1 main`

## git-forward

- Moves forward one commit in the git history
  - useful when wanting to proceed one commit at a time to see
    how changes affect your code
  - will not attempt to move forward beyond the branch HEAD
  - assumes `main` branch when no branch name is provided

Usage:

`git-forward [branch-name]`

## git-prune-local

- Identifies all remote branches and compares to local
- Any branch not found remotely will be offered for deletion
- Not automatic, you will have to individually accept each deletion
- Will skip branches with the `local/` prefix
  - these are assumed to be local only

## Suggestions

- For ease of use, add aliases to your bash profile to reference these scripts
  - E.g, `alias gcbr='~/path/to/scripts/git-cbranch'`
