# Git tups and trick

## Git diff

Useful command for comparing tags or branches. In this example we limit the diffs to a particular directory:

`git diff TagA..TabB --compact-summary .\src\frontend\Digital.Authentication.Service\`

Or to just get some overall stats:

`git diff TagA..TagB --shortstat`

## Git log

Nice simple history for the last n commits:

`git log --pretty=oneline -10`

