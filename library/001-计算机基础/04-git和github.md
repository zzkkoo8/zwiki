# git和github
>git是个工具github是git的托管服务器

[TOC]

## git入门
[官方教程](https://docs.github.com/cn/github "官方")
[廖雪峰大佬](https://www.liaoxuefeng.com/wiki/896043488029600 "廖雪峰")

## 建立文件夹git初始化
```
mkdir zwiki
cd zwiki
pwd
/Users/zzkk/zwiki
git init
git commit -m "first commit"
git remote add origin https://github.com/xxx.git
git push -u origin master,此时会要求输入用户名和密码
```

## 配置2个远程仓库，需要web页面上传ssh密钥公钥
```
git remote -v  //查看远程仓库
git remote rm origin
git remote add github git@github.com:xxx/yyy.git
git remote add gitee git@gitee.com:xxx/yyy.git
```

## gith日常
```
git add ./
git commit -m "0420"
git push origin master
```

## 命令大全
### git init
### git add
`git add ./  `  
`git add file2.txt file3.txt`  

### git commit
`git commit -m "add 3 files."`  

### git status
### git log  

查看历史，图形化，查看分支合并情况
`git log --graph --pretty=oneline --abbrev-commit`
分支合并图示  
`git log --graph`

### git reset
把暂存区的修改回退到工作区  
`git reset HEAD readme.txt`  
回退到上一个版本  
`git reset --hard HEAD^`  
回退到指定版本  
`git reset --hard 4e84e4`
### git reflog
回到未来，记录你的每一次命令  
### git diff
查看工作区和版本库里面最新版本的区别  
`git diff HEAD -- readme.txt`  
使用的是diff合并格式的变种，参考：  
http://www.ruanyifeng.com/blog/2012/08/how_to_read_diff.html
### git checkout
丢弃工作区的修改，让这个文件回到最近一次git commit或git add时的状态
`git checkout -- test.txt`  
切回master分支  
`git checkout master`  
在当前分支下创建并切换到dev分支  
`git checkout -b dev`  
创建从远程创建dev分支  
`git checkout -b dev origin/dev`

### git branch
查看、创建分支。  
`git checkout -b dev`一条命令等价于下面两个  
`git branch dev`  
`git checkout dev`  
删除分支  
`git branch -d dev`  
**强行删除**  
`git branch -D feature-vulcan`  
指定本地`dev`分支与远程`origin/dev`分支的链接  
`git branch --set-upstream-to=origin/dev dev`  

### git merge
合并dev分支到当前分支，当前已经切换在master分支  
`git merge dev`  
--no-ff参数，表示禁用Fast forward ，普通合并模式合并后的历史有分支
`git merge --no-ff -m "merge with no-ff" dev`  
### cherry-pick
复制一个特定的提交到当前分支  
`git cherry-pick 4c805e2`
### git switch
创建并切换到dev分支  
`git switch -c dev`  
直接切换到master  
`git switch master`
### git stash
临时存储工作现场  
`git stash list`  
恢复临时工作现场  
`git stash pop`  
等于  
`git stash apply + git stash drop`
### git rm
`git rm test.txt`或`git add test.txt`  
然后  
`git commit -m "remove test.txt"`
### git remote
查看远程仓库  
`git remote -v`  
添加远程仓库  
`git remote add origin git@github.com:michaelliao/learngit.git`  
删除远程仓库  
`git remote rm origin`

### git push
github是自定义的远程仓库名字，-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令  
`git push -u github master`  
`git push -u origin master`

`git push origin dev`  

### git clone
`git clone git@github.com:michaelliao/gitskills.git`  

### git pull  

抓取最新代码

### git rebase

把分叉的提交历史“整理”成一条直线

### git tag

`git show v0.9`

`git tag v1.0 f52c633`

建立带说明的标签

`git tag -a v0.1 -m "version 0.1 released" 1094adb`

先删除本地标签

`git tag -d v0.1`

再删除远程标签

`git push origin :refs/tags/v0.9`

推送全部标签

`git push origin --tags`

### 廖老师的命令大全
![廖老师的命令大全](https://liaoxuefeng.gitee.io/resource.liaoxuefeng.com/git/git-cheat-sheet.png "Title")