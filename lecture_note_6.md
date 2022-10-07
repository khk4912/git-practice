# Lab 6 (Basic `git` commands)

## git config

`git config` is used to set the configuration variables that control all aspects of how Git looks and operates. These variables can be stored in three different places:

- System level (`/etc/gitconfig`)
- User level (`~/.config/git/config`)
- Local level (`.git/config`)

Each level overrides values in the previous level.
(System -> User -> Local)

## Initialize a repository

`git init` creates a new Git repository.

```sh
❯ git init
Initialized empty Git repository in /Users/khk4912/Code/GitPractice/.git/
```

## Chekcing repository status

`git status` shows the working tree's status.

```sh
❯ git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        migration_db.py

nothing added to commit but untracked files present (use "git add" to track)
```

## Adding files to staging area

`git add` adds changes in the working directory to the staging area.  
Stagaing is mandatory before commmiting.

```sh
❯ git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	migration_db.py

nothing added to commit but untracked files present (use "git add" to track)
❯
❯ git add migration_db.py
❯
❯ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   migration_db.py
```

## Ignoring files

`.gitignore` is a file that tells Git which files (or patterns) it should ignore.

```sh
# Ignore all .a files
*.a

# But do track lib.a, even though you're ignoring .a files above
!lib.a

# Ignore all files in the build/ directory
build/

# Ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# Ignore all .pdf files in the doc/ directory
doc/**/*.pdf
```

## Committing changes

`git commit -m "message"` commits the staged snapshot to the project history.

```sh
❯ git commit -m "initial commit"
[main (root-commit) e79e713] initial commit
 1 file changed, 105 insertions(+)
 create mode 100644 migration_db.py
❯
❯ git status
On branch main
nothing to commit, working tree clean
```

## Change branch name

`git branch -m [previous name] [new name]` changes the branch name.
