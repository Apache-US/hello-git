## git基本命令

```
git config --global user.name "zhaohe"`                      # 配置用户名
 `git config --global user.email "1013909206@xqq.com"`              # 配置邮件
 `git config --global color.ui true`                         # git status等命令自动着色
 `git config --global color.status auto`
 `git config --global color.diff auto`
 `git config --global color.branch auto`
 `git config --global color.interactive auto
```

`git init`              #初始化仓库
 `git add 文件名`               #将更改过的文件放至暂存区（index）
 `git commit -m "描述信息"`   #提交
 `git status`               #查看当前版本状态（是否修改）
 `git log`              #显示提交日志
 `git rm XXX`               #删除index中的文件

`git diff`             #显示所有未添加至index的变更
 `git diff --cached`                      # 显示所有已添加index但还未commit的变更
 `git diff HEAD^`                      # 比较与上一个版本的差异
 `git diff HEAD^ HEAD`                  # 比较上次和上上次版本的差异
 `git diff origin/master..master`         # 比较远程分支master上有本地分支master上没有的

`git reset --hard （commit值）`        #将当前版本重置为commit号对应的版本
 `git mv README README2`                  # 重命名文件README为README2

`git branch`                                             # 显示本地分支
 `git branch develop`       #创建develop分支
 `git branch -d develop`         #删除development分支

`git push`可以提示帮助

`git checkout master`           #切换到master分支上
 `git merge origin/master`           # 合并远程master分支至当前分支
 `git push origin master`                  # 将当前分支push到远程master分支
 `git push --tags`           # 把所有tag推送到远程仓库
 `git pull origin master`                  # 获取远程分支master并merge到当前分支

## git三个工作区和文件的四种状态

工作目录（workspace）、暂存区（index）、本地仓库（repo）
 未跟踪（untracked）、已暂存(staged)、已修改(modified)、已提交(committed)

1）当在工作目录中新加入一个文件时，它处于未跟踪状态，这表示其没有纳入Git的版本控制。
 2）通过 git add 命令可以将其加入跟踪，并同时放入暂存区。
 3）一个已经被跟踪的文件，如果没有做过新的修改，就是未修改状态。
 4）一旦对其做了改动，就变成了已修改状态。通过 git add 命令可以将已修改的文件放入暂存区。
 5)初次克隆某个仓库时，工作目录中所有文件都是已跟踪且未修改的状态。
 6)git commit 命令会将暂存区中的文件提交至HEAD所指向的分支。当被commit之后，暂存区的文件将回到未修改状态。

## git分支

git branch              查看
 git checkout                切换分支
 git branch -d develop           删除development分支
 git branch -m develop   iii     重命名

git merge 分支名           合并分支

合并时冲突

## git远程服务器

[git服务器搭建](https://link.jianshu.com?t=http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137583770360579bc4b458f044ce7afed3df579123eca000/)

git.oschina.net

1.注册激活
 2.添加公钥
 3.创建项目
 4.创建新的分支并修改文件
 5.推送分支和代码到远程仓库
 6.更新远程仓库的分支和代码到本地

[git@git.oschina.net](https://link.jianshu.com?t=mailto:git@git.oschina.net):farsght160421_1/farsight160421-1.git

## git技巧

### git .使用技巧

你是不是很烦那些编译过的文件 (比如 .pyc) 出现在你的 Git 仓库中？或者说你已经受够了已经把它们都加进了 Git 仓库？好了，这有个办法可以让你告诉 Git 忽略掉那些特定的文件和文件夹。只需要创建一个名为 .gitignore 然后列出那些你不希望 Git 跟踪的文件和文件夹。你还可以添加例外，通过使用感叹号(!)。

*.pyc
 *.exe
 ^.*
 !.git
 !main.pyc
 !.gitignore

# git命令分类

## git信息查看相关指令

git branch 查看分支

git branch -a 查看全部分支

git status 查看状态

git log 查看提交日志

git reflog  查看全部提交日志

git remote -v 查看远程

