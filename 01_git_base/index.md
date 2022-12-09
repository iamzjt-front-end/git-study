# 01_git_base

### 1. 在现有目录中初始化仓库

```shell
git init
```

会创建一个名为`.git`的子目录，这个目录含有你初始化Git仓库所有的必须文件。

### 2. 克隆现有仓库

```shell
# 克隆仓库
git clone https://github.com/libgit2/libgit2

# 克隆并重命名
git clone https://github.com/libgit2/libgit2 myLibgit
```

### 3. 检查当前文件状态

```shell
git status
```

### 4. 跟踪新文件

```shell
git add README.md
```

### 5. 暂存已修改文件

```shell
# 当修改已经add过后的文件时，这个文件会同时存在于暂存区和非暂存区
git add README.md
```

实际上`Git`只不过是暂存了你运行`git add`时的版本，如果你现在提交，`README.md`的版本是你最后一次运行`git add`时的那个版本，而不是你运行`git commit`时，在工作目录中的当前版本。所以，运行`git add`后又做了修改的文件，需要重新运行`git add`将最新版本重新暂存起来。

### 6. 状态简览

```shell
# git status --short
git status -s
```

### 7. 忽略文件

```shell
cat .gitignore
```

### 8. 查看已暂存和未暂存的修改

```shell
# 此命令比较的是工作目录中当前文件和暂存区域快照之间的差异，也就是修改之后还没暂存起来的变化内容
git diff

# 若要查看已暂存的将要添加到下次提交里的内容
git diff --staged
```

### 9. 提交更新

```shell
git commit
git commit -m ''
```

### 10. 跳过使用暂存区

```shell
git commit -a -m ''
```

### 11. 移除文件

```shell
# 准确的说是从暂存区移除文件
git rm PROJECTS.md
```