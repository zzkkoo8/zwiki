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

## gith日常提交
```
git add ./
git commit -m "0420"
git push origin master
```

## 命令大全详解
### git init
### git add file2.txt file3.txt
### git commit -m "add 3 files.
### git status
### git diff
### git log
git log --pretty=oneline
### git reset
git reset --hard HEAD^
git reset --hard 4e84e4


git diff使用的是diff合并格式的变种，参考：
http://www.ruanyifeng.com/blog/2012/08/how_to_read_diff.html
