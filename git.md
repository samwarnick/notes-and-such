# Git

**Table of Contents**
* [Branches](#branches)
  * [Deleting](#deleting)

## Branches

### Deleting

**Delete all merged branches**

`git branch --merged | egrep -v "(^\*|master|dev)" | xargs git branch -d`

[Source](https://stackoverflow.com/a/6127884/6111857)
