# Git使用

### git代码分支操作

#### git push origin --delete refs/heads/localDev   # 删除远程分支

####  git push --set-upstream origin remotes/origin/localDev  # 设置本地关联远程分支

> git branch --set-upstream-to=origin/remote_branch local_branch

#### git branch -m remotes/origin/localDev localDev   # 对本地分支进行重命名


#### git branch -a   # 列出所有分支
#### git push origin :remotes/origin/localDev   # 删除远程分支，如果省略本地分支名，则表示删除指定的远程分支，因为这等同于推送一个空的本地分支到远程分支
remote: Powered by GITEE.COM [GNK-5.0]
To iisfree.gitee:leelongcrazy/mushroom.git

[deleted]         remotes/origin/localDev
iisfree@DESKTOP-EOLISFD /mnt/d/mushroom
#### git push origin localDev:Dev    # 将本地分支名推送到指定远程分支名
Counting objects: 967, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (687/687), done.
Writing objects: 100% (967/967), 4.84 MiB | 8.31 MiB/s, done.
Total 967 (delta 360), reused 710 (delta 263)
remote: Resolving deltas: 100% (360/360), completed with 11 local objects.
remote: Powered by GITEE.COM [GNK-5.0]
remote: Create a pull request for 'Dev' on Gitee by visiting:
remote:     https://gitee.com/leelongcrazy/mushroom/pull/new/leelongcrazy:Dev...leelongcrazy:master
To iisfree.gitee:leelongcrazy/mushroom.git

[new branch]      localDev -> Dev

## Git拉取远程分支的代码到本地

``` bash
# 1.
git fetch origin remote_branch_name
# 2. 
git pull origin remote_brach_name
```

## git tag 操作
``` bash
# 远程tag分支
git ls-remote --tags origin

# 列出本地tag
git tags

# 创建
git tag [tag Name]
git tag -a [tag Name] -m desc

# 推送tag到远程仓库
git push origin --tags
# 推送指定本地tag到远程
git push origin [local tag name]

# 删除本地tag
git tag -d [tag name]
# 删除远程tag
git push origin :refs/tags/[remote tag name]

# 拉取远程指定tag
git fetch origin [remote tag name]

# 显示指定tag详细信息
git show [tag name]
```

