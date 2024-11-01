# Homebrew Command

> Homebrew 指令

## 1. brew 安装

<https://brew.sh/>

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 2. 常用指令

### 1. 查看

```bash
# 查看brew的版本
brew -v

# 查看命令帮助：
brew -help

# 查看安装列表
brew list

# 查询可用包
brew search [包名]
# 例：brew search git

# 查看包信息
brew info [包名]
# 例：brew info git

# 显示包依赖
brew deps [包名]
# 例：brew deps git
# 例：brew deps --installed --tree  # 查看已安装的包的依赖，树形显示

# 查找软件安装位置
which xxx  # xxx为软件名称
```

### 2. 安装/卸载

```bash
# 安装软件包 # 安装一些不带界面的命令行工具和第三方库
brew install [包名]@版本
# 例：brew install git

# 卸载软件包
brew uninstall [包名]
# 例：brew uninstall git
# 例：brew uninstall --force $FORMULA  # 删除所有版本

# 安装软件 # 安装一些带界面的应用软件
brew cask install xxx  # xxx为软件名称

# 卸载软件
brew cask uninstall xxx

# 卸载
brew rm $FORMULA   # 卸载某个包
# 例：brew rm node
# 例：brew rm node ruby  # 卸载多个包
# 例：brew rm --ignore-dependencies node  # 保留删除包的依赖项 
```

### 3. 更新

```bash
# 更新 homebrew 自己
brew update

# 查看那些已安装的程序需要更新
brew outdated

# 更新`所有`软件
brew upgrade

# 更新`单个`软件
brew upgrade [包名]
# 例：brew upgrade git

# 锁定不想更新的包
brew pin $FORMULA  # 锁定某个包
brew unpin $FORMULA  # 取消锁定
```

### 4. 清理旧版本

```bash
# 清理所有包的旧版本（安装包缓存）
brew cleanup 
# 例：brew cleanup -n  # 显示要删除的内容，但不要实际删除任何内容
# 例：brew cleanup -s  # 清理缓存，包括下载即使是最新的版本
# 例：brew cleanup --prune=1     # 删除所有早于指定时间的缓存文件（天）

# 清理单个软件旧版本
brew cleanup [包名]
# 例：brew cleanup git 

# 查看可清理的旧版本包，不执行实际操作
brew cleanup -n 
```

