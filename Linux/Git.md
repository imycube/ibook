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

添加tag描述: git tag -a <tagname> -m "runoob.com标签"

删除tag: git tag -d [tag]

删除远程tag : git push origin :refs/tags/[tag] 

添加文档：git add file ...

添加所有文件： git add .

填写备注到缓存区： git commit -m "fix/feat"

取消本次commit并舍弃修改: git reset --hard HEAD^

取消本次commit保留修改： git reset --soft HEAD^

取消文件commit： git reset HEAD demo1

还原到某个版本快照： git restore

将版本回退到当前快照的前一个版本: git restore -s HEAD~1 READEME.md

指定明确的 commit id 回退到指定的快照: git restore -s 91410eb9  READEME.md

撤销 commit 至上一次 commit : git reset --soft HEAD^

提交到远程： git push

远程拉取 ： git pull

合并后并产生commit记录： git merge feature/branch  

合并不产生合并记录： git rebase master -i

获取develop的commit合并到当前branch: git pull origin develop

---
## log日志
| 功能 | 命令 |
| ---- | ---- |
| 查看所有 | git log |
| 一行显示 | git log --oneline |
| 显示几条 | git log -[length] |
| 显示更多信息 | git log –pretty=raw |
| 显示提交的改动记录 | git log -p |
| 提交的记录 | git log --graph --oneline |
| 显示分支/tag | git log --decorate |
| 显示对应文件改动 | git log --name-status --oneline |
| 搜索人员 | git log --author name |
| 关键字搜索 | git log --grep keyword |
| 文件名称过滤 | git log -p -- filename |
