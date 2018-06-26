# Git

**Table of Contents**
* [Branches](#branches)
  * [Deleting](#deleting)
* [Command Line](#command-line)

## Branches

### Deleting

**Delete all merged branches**

`git branch --merged | egrep -v "(^\*|master|dev)" | xargs git branch -d`

[Source](https://stackoverflow.com/a/6127884/6111857)

## Command Line

**Search for something before committing**

`git diff -G console`

[Source](https://twitter.com/exkuchme/status/1011481635169042432?s=21)
