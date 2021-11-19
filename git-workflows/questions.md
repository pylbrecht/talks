# Questions
## Which option do you need to pass to `git add`, in order to interactively choose hunks to add them to the index?
`--patch`

## Which git command triggers an interactive rebase?
`git add --interactive/-i`

## Name two operations you can perform on commits during an interactive rebase.
You can..
- reorder commits
- squash commits
- reword commits
- delete/drop commits
- edit commits (not part of the talk, but still counts)
- fixup commits (not part of the talk, but still counts)

## How do you configure your editor/IDE of choice as git's default editor?
Either by setting the corresponding config entry
```
# --global can be omitted if one wants to configure the editor per project
$ git config --global core.editor "path/to/executable"
```
or via setting the corresponding environment variable
```
export GIT_EDITOR=path/to/executable
```

# Bonus questions
These questions are not covered by the talk and therefore require further
research (hence "bonus"). They should serve as food for thought for the curious
folks, who want to dive deeper into the topic.

## Name two git commands besides `git add`, which also take the `--patch` option.
1. `git checkout`
2. `git reset`

(there may be even more, but these are two I know from the top of my head)

## Why are the commits in `git rebase -i`'s output listed in reversed order compared to `git log`'s output?
The interactive rebase gives you a script that it’s going to run. It will start
at the commit you specify on the command line and replay the changes
introduced in each of these commits from top to bottom. It lists the oldest at
the top, rather than the newest, because that’s the first one it will replay.
(source https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
