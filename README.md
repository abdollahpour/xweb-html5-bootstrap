# XWeb HTML5 based on bootstrap

You can create XWeb applications in minuets!

## Requirements
* JDK (JDK 7+)
* Maven (Version 3.0+)
* GIT

## Start
This document is for Linux but it also work with other operation systems.

First, you need to create your own git repository
`git init`

Second, add xweb-bootstrap as upstream of your project
`git remote add upstream https://github.com/abdollahpour/xweb-html5-bootstrap.git`

Thirds, OK! You can make your changes right now!

## Notes
* For more information about xweb modules and configurations go to (xweb wiki)[https://github.com/abdollahpour/xweb/wiki]
* Because project it under heavy development right now, maybe you need to track change from main repository also:
`git fetch upstream'

Then you need to merge it with master (and maybe resolve conflicts)
```
git checkout master
git merge upstream
```