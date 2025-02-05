## git修改远程仓库地址

`git remote -v`     查看关联远程仓库地址

`git remote set-url origin 新的地址`      修改远程仓库地址

`git remote -v`     查看是否修改成功



## git clone 远程仓库的某个分支

`git clone -b 分支名 xxx.git`



## 远程分支改变，如何同步本地？

```shell
git branch -m master main
git fetch origin
git branch -u origin/main main
git remote set-head origin -a
```



## git强制提交本地代码到远程

```shell
git init
git remote add origin 远程仓库地址
git add . 
git commit -m “添加注释信息"
#强制提交
git push -u origin master -f 
```



## 版本回退

```shell
#查看历史提交日志
git log  
git log --pretty=oneline
#查看历史命令
git reflog
#回退指定版本
git reset --hard commit_id
##HEAD代表当前版本，一个^代表向上回退一个版本
git reset --hard HEAD^
```



## 中文乱码问题

```shell
# git status 乱码
git config --global core.quotepath false

#git commit 乱码
git config --global i18n.commitencoding utf-8

#git status 乱码
git config --global i18n.logoutputencoding utf-8
```

注意：如果是Linux系统，需要设置环境变量 `export LESSCHARSET=utf-8`

[Git for windows 中文乱码解决方案](https://www.cnblogs.com/ayseeing/p/4203679.html)



## git在.gitignore添加忽略文件不起作用

```shell
git rm -r --cached .
```

重新`add`和`commit`即可解决
