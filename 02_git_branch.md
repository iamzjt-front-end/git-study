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