## Git

Git is a distributed version control system that tracks changes in code.

**Distributed** → Each user has a complete copy of the project's history and code on their local machine, rather than relying on a central server for all versioning information.

## GitHub

GitHub is a cloud-based hosting service for Git repositories.

## Key Git Concepts

- **Working Directory** → Where you edit files.
- **Stage** → which changes to be included in the next commit.
- **Local Repository**→ A folder where Git tracks your project and its history.
- **Remote Repository** → GitHub/other hosting service.
- **Commit** → Save a snapshot of your staged changes.
- **Clone** → Make a copy of a remote repository on your computer.
- **Branch** → Work on different versions or features at the same time.
- **Merge** → Combine changes from different branches.
- **Pull** → Get the latest changes from a remote repository.
- **Push** → Send your changes to a remote repository.
- **Untracked File** → Any file in your project folder that Git is not yet tracking. These are files you've created or copied into the folder, but haven't told Git to watch.
- **Tracked File** → A tracked file is a file that Git is watching for changes. To make a file tracked, you need to add it to the staging area.

## Common Commands

| Command               | Purpose                                   |
| --------------------- | ----------------------------------------- |
| `git init`            | Initialize a new repo                     |
| `git clone <url>`     | Copy repo from remote                     |
| `git status`          | Show tracked/untracked changes            |
| `git add <file>`      | Stage changes                             |
| `git commit -m "msg"` | Save staged changes to local repo         |
| `git push`            | Upload commits to remote                  |
| `git pull`            | Fetch + merge from remote                 |
| `git fetch`           | Only fetch changes from remote (no merge) |
| `git branch`          | List branches                             |
