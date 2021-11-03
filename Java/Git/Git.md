# Git

## 常用命令

查看版本 : git --version 

检出项目 : git clone project-url.git 

查看分支情况 : git branch 

查看分支对应远程 : git branch -vv

检出新分支 : git checkout -b feature/newbranch

设置新分支远程: git push --set-upstream origin feature/newbranch

切换分支： git checkout feature/branch

删除本地分支: git branch -D feature/branch

删除远程分支： git push origin --delete feature/branch

添加tag: git tag [tag]

删除tag: git tag -d [tag]

删除远程tag : git push origin :refs/tags/[tag] 