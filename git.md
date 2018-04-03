# Git

## Neat Stuff

### Delete all merged branches
git branch --merged | egrep -v "(^\*|master|dev)" | xargs git branch -d
(from [StackOverflow](https://stackoverflow.com/a/6127884/6111857))
