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