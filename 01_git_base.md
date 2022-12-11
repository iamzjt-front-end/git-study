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
git commit -am ''
```

### 11. 移除文件

```shell
# 从暂存区和工作目录一起删除文件
git rm PROJECTS.md

# 仅从暂存区删除文件
git rm --cached PROJECTS.md

# ps: 删除文件夹 需要加 -r
# ps: 对于已加入缓存区并且后续又进行修改过的文件，需要加-f，强制删除
```

### 12. 移动文件(改名)

```shell
git mv index.md index1.md

# 其实，运行 git mv 相当于运行了下面三条命令：
mv index.md index1.md
git rm index.md
git add index1.md
```

### 13. 查看提交历史

```shell
git log

# 可以显示出每次提交的差异
git log -p

# 也可以加上-2显示最近两次提交
git log -p -2

# 附带有总结
git log --stat

# --pretty 可以指定使用不同于默认格式的方式展示提交历史
git log --pretty=oneline

# --pretty=format:"" 定制要显示的记录格式
git log --pretty=format:"%h - %an, %ar : %s"

# --graph 展示分支、合并历史
git log --pretty=format:"%h $s" --graph
```