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

### 13. 撤销操作

```shell
# 修改提交信息
git commit --amend
```

### 14. 取消暂存的文件

```shell
# 也就是取消对文件的add操作
git reset HEAD index.md
```

### 15. 撤销对文件的修改

```shell
# 撤销修改，还原成上次提交的样子
git checkout -- index.md
```

### 16. 查看远程仓库

```shell
# 克隆远程仓库
git clone https://github.com/schacon/ticgit

# 查看仓库源及url
git remote -v
```

### 17. 添加远程仓库

```shell
# 添加仓库源，并且可以在命令行中使用字符串 pb 来代替整个 URL
git remote add <shortname> <url>
git remote add pb https://github.com/paulboone/ticgit
```

### 18. 从远程仓库中抓取与拉取

```shell
git fetch [remote-name]
# 默认仓库源简写的origin
# 会抓取克隆（或上一次抓取）后新推送的所有工作，它并不会自动合并或修改你当前的工作
git fetch origin

git pull
```

### 19. 推送到远程仓库

```shell
git push origin main
```

### 20. 查看远程仓库

```shell
git remote show origin
```

### 21. 远程仓库的重命名与移除

```shell
git remote rename pb paul

git remote rm paul
```

### 22. 打标签

```shell
# 列出标签
git tag

# 查找特定的标签
git tag -l 'v1.8.5*'
```

### 23. 创建标签及附注

```shell
git tag -a v1.4 -m 'my version 1.4'

# 查看标签信息及对应的提交信息
git show v1.4
```

### 24. 轻量标签

```shell
git tag v1.4-lw

git show v1.4-lw
```

### 25. 后期打标签

```shell
git log --pretty=oneline

git tag -a v1.2 9fceb02
```

### 26. 共享标签

```shell
git push origin v1.5
git push origin --tags
```

### 27. 检出标签

```shell
git checkout -b version2 v2.0.0
```

### 28. Git别名

```shell
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```