# 02_git_branch

### 1. 分支创建

```shell
git branch testing
```

### 2. 分支切换

```shell
git checkout testing01
```

### 3. 新建分支及切换

```shell
git checkout -b testing02

# 相当于两条命令的缩写
git branch testing02
git checkout testing02
```

### 4. 分支合并

```shell
git checkout main
git merge testing02
```

### 5. 分支管理

```shell
# 分支查看
git branch

# 查看分支及最后一次提交
git branch -v

# 分支删除
git branch -d demo

# 推送分支
git push origin demo
```

### 6. 远程分支

```shell
# 删除远程分支
git push origin --delete serverfix
```

### 7. 变基

```shell
git checkout main
git rebase testing
```