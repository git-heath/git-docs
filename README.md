# Git tips and trick

## Git diff

Useful command for comparing tags or branches. In this example we limit the diffs to a particular directory:

`git diff TagA..TagB --compact-summary .\src\My-App\`

Or to just get some overall stats:

`git diff TagA..TagB --shortstat`

## Git log

Nice simple history for the last n commits:

`git log --pretty=oneline -10`

