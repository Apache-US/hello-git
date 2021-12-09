### hello git


在命令行进入到 ~/workspace/git_repos/hello-git]$ 才能执行以下命令



##### git 常用命令

```
git version #查看git版本命令
```

##### 一些常用别名配置

配置用户名 git config --global user.name "your_name"

配置邮箱: git config --global user.email "your_email"

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

##### 撤消暂存区

```
git rm --cached #文件颜色会变红,表示未提交到暂存区
```

可以在隐藏文件 .git 中查看index 文件 

##### git 提交到本地仓库区

```
git commit -m "add more"
```

#### git push 提交到远程仓库

```
git push origin master -u 
#-u 的意思今后只要git push就行了,不用在加origin master这样的参数了
```

------

##### git clone 克隆

如果目录存在会提示文件已经存在, 可以在网址后面加上空格,新的文件名既可

```
git clone https://github.com/Apache-US/git-tutorial.git
```

进入到git-demo 新文件名

##### git checkout -- file name 还原上一个状态

##### git pull 拉取仓库 

如果文件未提交状态无法提交,操作 git add -A , git commit -m "" 后再拉取
