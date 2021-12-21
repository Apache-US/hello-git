## 更新命令

更新 `Homebrew` 自己

```
brew update
```

### 查看哪些安装包需要更新

```
brew outdated
```

### 更新安装包

```
brew upgrade   # 更新所有的包
brew upgrade $FORMULA   # 更新指定的包
```

### 清理旧版本

```
brew cleanup   # 清理所有包的旧版本
brew cleanup $FORMULA   # 清理指定包的旧版本
brew cleanup -n   # 查看可清理的旧版本包，不执行实际操作
```

### 锁定不想更新的包

```
brew pin $FORMULA   # 锁定某个包
brew unpin $FORMULA    # 取消锁定
```

### 查看安装包的相关信息

```
brew info $FORMULA   # 显示某个包的信息
brew info   # 显示安装了包数量，文件数量，和总占用空间
brew deps --installed --tree   # 查看已安装的包的依赖，树形显示
```

## 其他

### 列出已安装包

```
brew list
```

### 删除

```
brew rm $FORMULA   # 删除某个包
brew uninstall --force $FORMULA   # 删除所有版本
```





------





##### 更新 Homebrew



```cpp
//更新包
brew update
```

更新之前，先查看哪些包可以更新。



```bash
brew outdated         #会安装新版本的包，但旧版本仍然会保留。
brew upgrade             # 更新所有的包
brew upgrade $FORMULA    # 更新指定的包
```

一般情况下，新版本安装了，旧版本就不需要了。用brew cleanup 清理旧版本和缓存文件。Homebrew 只会清除比当前安装的包更老的版本，所以不用担心有些包没更新但被删了。



```bash
brew cleanup             # 清理所有包的旧版本
brew cleanup $FORMULA    # 清理指定包的旧版本
brew cleanup -n          # 查看可清理的旧版本包，不执行实际操作
锁定不想更新的包
```

如果经常更新的话，brew update 一次更新所有的包是非常方便的。但我们有时候会担心自动升级把一些不希望更新的包更新了。数据库就属于这一类，尤其是 PostgreSQL 跨 minor 版本升级都要迁移数据库的。我们更希望找个时间单独处理它。这时可用 brew pin 去锁定这个包，然后 brew update 就会略过它了。



```bash
brew pin $FORMULA      # 锁定某个包
brew unpin $FORMULA    # 取消锁定
```

#### 其他几个常用命令

brew info 可以查看包的相关信息，最有用的应该是包依赖和相应的命令。比如 Nginx 会提醒你怎么加 launchctl ，PostgreSQL 会告诉你如何迁移数据库。这些信息会在包安装完成后自动显示，如果忘了的话可以用这个命令很方便地查看。



```bash
brew info $FORMULA    # 显示某个包的信息
brew info             # 显示安装了包数量，文件数量，和总占用空间
brew deps           #可以显示包的依赖关系，我常用它来查看已安装的包的依赖，然后判断哪些包是可以安全删除的。
```



```bash
brew deps --installed --tree # 查看已安装的包的依赖，树形显示
输出如下：
```

gcc
 ├── gmp
 ├── libmpc
 │   ├── gmp
 │   └── mpfr
 │       └── gmp
 ├── mpfr
 │   └── gmp
 └── isl
 └── gmp

gdbm

git

gmp

isl
 └── gmp

libmpc
 ├── gmp
 └── mpfr
 └── gmp



作者：隔墙送来秋千影
链接：https://www.jianshu.com/p/d2f8ed1127a3
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。