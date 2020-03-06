# Git tips and tricks

## Git diff

Useful command for comparing tags or branches. In this example we limit the diffs to a particular directory:

`git diff TagA..TagB --compact-summary .\src\My-App\`

Or to just get some overall stats: `git diff TagA..TagB --shortstat`

**Useful**: To list tags in order for a repo: `git tag --list 'Nameof.Application*' --sort v:refname`

## Deleting a remote tag

Useful command: `git push origin :refs/tags/MyTag-20.01.16-dev`

## Git log

Nice simple history for the last n commits:

`git log --pretty=oneline -10`

## Rebase

Note that in github when completing a pull request with a rebase when master has not advanced you would expect the SHA1 of the
resultant HEAD to be the same as the tip of your merged branch but this is not the case as the committer changes. This is unique 
to github and can be seen explicity using one of the following git log commands:

- `git log --pretty=format:"%H, Author:%an, Committer:%cn, message:%s"`
- `git log --format=fuller`

Here we see the author and the committer and how they differ when completing a PR in Github. If you try the same command with an Azure DevOps git repository you will see that the Auther=Committer. A good explanation of this for Github is given here [rebase and merge pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-request-merges#rebase-and-merge-your-pull-request-commits). The difference between author and committer is also described [here](https://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History)

## Cleaning

If your local git is in a bad state and you want to dump everything locally and sync with the origin (for example a rebase gone wrong):

`git reset --hard origin/features/myBranch`

Even after doing this you may still have some untracked files (in working tree). To remove these you can use the git clean option.

- `git clean -n` : Check what you are going to clean
- `git clean -f` : Do the actual cleaning (removing) of files

