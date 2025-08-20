## Git

Git is a distributed version control system that tracks changes in code.

**Distributed** → Each user has a complete copy of the project's history and code on their local machine, rather than relying on a central server for all versioning information.

## GitHub

GitHub is a cloud-based hosting service for Git repositories.

## Key Git Concepts

- **Working Directory** → Where you edit files.
- **Stage** → which changes to be included in the next commit.
- **Local Repository**→ A folder where Git tracks your project and its history.
- **Remote Repository** → It is a version of your project's repository that is hosted on a server or a code hosting service like GitHub,
- **Commit** → Save a snapshot of your staged changes.
- **Clone** → Make a copy of a remote repository on your computer.
- **Branch** → A branch represents an independent line of development within a repository. It allows to work on different versions or features at the same time.
- **Merge** → Combine changes from different branches.
- **Pull** → Get the latest changes from a remote repository.
- **Push** → Send your changes to a remote repository.
- **Untracked File** → Any file in your project folder that Git is not yet tracking. These are files you've created or copied into the folder, but haven't told Git to watch.
- **Tracked File** → A tracked file is a file that Git is watching for changes. To make a file tracked, you need to add it to the staging area.

## Common Commands

| Command                        | Purpose                                     |
| ------------------------------ | ------------------------------------------- |
| `git init`                     | Initialize a new repo                       |
| `git clone <url>`              | Copy repo from remote                       |
| `git status`                   | Show tracked/untracked changes              |
| `git add <file>`               | Stage changes                               |
| `git commit -m "msg"`          | Save staged changes to local repo           |
| `git push`                     | Upload commits to remote                    |
| `git pull`                     | Fetch + merge from remote                   |
| `git fetch`                    | Only fetch changes from remote (no merge)   |
| `git log`                      | View commit history                         |
| `git diff`                     | Show unstaged changes                       |
| `git checkout <branch/commit>` | Switch branch or commit                     |
| `git branch`                   | List branches                               |
| `git merge <branch>`           | Merge branch into current                   |
| `git reset`                    | Undo commits/staging                        |
| `git revert <commit>`          | Create a commit that undoes changes         |
| `git stash`                    | Temporarily save changes without committing |

## Branching & Merging

- **Branch** → Independent line of development.
- **Fast-forward merge** → When current branch is directly ahead of target.
- **Three-way merge** → When branches have diverged.
- **Merge conflicts** → Occur when changes affect same part of a file; must be resolved manually.
- **Rebase** → Moves commits to start from another base commit (cleaner history).

## Git Reset vs Revert vs Checkout

- **reset** → Moves HEAD to a specific commit, changes history (use with caution).
- **revert** → Safely undoes a commit by creating a new one.
- **checkout** → Switch branch/commit or restore files.

## Remote Repositories

- **origin** → Default remote name.
- **upstream** → Original repo from which a fork was made.
- `git remote -v` → Show remotes.
- `git push origin main` → Push changes to main branch.

## GitHub Collaboration Workflow

- Fork → Clone → Create branch → Make changes → Commit → Push → Create Pull Request (PR) → Code review → Merge → Delete branch.

## Stash

- `git stash` → Save uncommitted changes.
- `git stash pop` → Apply latest stash & remove it.
- `git stash list` → View saved stashes.

## Tags

- **Lightweight tag** → Points to a commit.
- **Annotated tag** → Includes metadata.
- `git tag v1.0` → Create tag.
- `git push origin v1.0` → Push tag to remote.

## Ignoring Files

- `.gitignore` → List of files/folders Git should ignore.
- Useful for secrets, build files, `node_modules/`.

## Common Interview Q\&A

**Q:** Difference between `git fetch` and `git pull`?
**A:** `fetch` downloads commits but doesn’t merge; `pull` = fetch + merge.

**Q:** How to resolve merge conflicts?
**A:** Open conflicting files, manually fix changes, `git add` and `git commit`.

**Q:** Difference between merge and rebase?
**A:** Merge keeps history as branches; rebase rewrites commits to create linear history.

**Q:** How to undo last commit but keep changes?
**A:** `git reset --soft HEAD~1`.

**Q:** How to see who changed a line in a file?
**A:** `git blame <file>`.

## Best Practices

- Commit often, but with meaningful messages.
- Use feature branches instead of committing to `main`.
- Keep `main` branch stable.
- Pull before pushing to avoid conflicts.
- Never force-push to shared branches unless necessary.
