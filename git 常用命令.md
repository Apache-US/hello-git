##### git 常用命令

```
git version #查看git版本命令
```

##### 一些常用别名配置

http and https 代理被墙仓库

```
vi ~/.gitconfig
```

``` bash
        name = apache_us
        email = pauladgale127@gmail.com
[color]
        ui = true
[alias]
        co = checkout
        br = branch
        ci = commit
        st = status
        unstage = reset HEAD --
[http]
        proxy = 127.0.0.1:7890
[https]
        proxy = 127.0.0.1:7890
```
##### 查看文件状态

```
 git status
```

```bash
On branch master #分支状态
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   "git \345\270\270\347\224\250\345\221\275\344\273\244.md" #更改过未提交的文件红色表示

no changes added to commit (use "git add" and/or "git commit -a")
```

##### git 提交到转存区

```
git add file name
git add -A #the same as above
#提交文件到暂存区后 git status 看一下文件名会变绿
```







