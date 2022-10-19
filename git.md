## 记录一些常用的git命令以及git工作流

### 一、基本命令

#### 配置命令

``` js
git config --list   // 查看config信息
git config --global core.safecrlf false // 去除CR LE提示信息
git config --global user.name 'your name' // 设置username
git config --global user.email 'your email' //设置邮箱
git config --global alias.ci commit // 将commit命令设置为别名ci，也可以设置其他别名
```

#### 使用命令

``` js
git add .  // 将工作区的所有文件添加到git 暂存区
git commit -m 'commit message' // 提交信息，将文件保存到本地仓库
git commit -a -m 'commit message' // 结合 add 和 commit
git status // 查看文件状态
git log // 查看提交记录
git log --pretty=oneline // 一行显示提交记录
git log --pretty-oneline graph // 图形化显示提交记录
git reflog // 显示所有的提交(包括回退)
git push origin -u master// 推送本地仓库到远程仓库
git push --force // 强制推送
git pull <远程主机名> <远程分支名>:<本地分支名> // 从远程仓库拉去代码

```

#### 分支命令

```  js
git branch // 查看本地分支
git branch 分支名 // 新建分支
git checkout 分支名 // 切换分支
git checkout -b 分支名 // 新建并切换分支
git cherry-pick commitId // 把其他分支的某次提交合并到该分支
git branch -d 分支名 // 删除分支
git branch -D 分支名 // 强制删除分支
git branch -m o分支名 n分支名 // 修改分支名
git branch -r // 查看远程分支
git branch -a // 查看所有远程分支和本地分支
git push origin --delete 分支名 // 将本地删除的分支同步到远程仓库
git remote show origin // 查看remote地址
git remote prune origin // 删除远程仓库不存在的分支
```

#### 标签命令

``` js
git tag // 查看标签
git tag -d 标签名 // 删除对应标签
git tag 标签数字 // 在当前仓库打标签
git tag 标签名 commitId // 给指定提交打标签
git tag -l // 过滤tag
git show 标签名称 // 展示tag的详情信息
git push origin 标签名称 // 同步tag到远程仓库
git push origin --tags // 将本地所有tag推送到远程
git pull --tags // 将远程仓库的标签也拉取

git stash // 把暂存区内容，暂时保存起来
git stash list // 查看stash内容
git stash pop // 恢复stash内容，并删除
git stash apply // 恢复stash内容，不会删除
git stash clear // 清除所有缓存statsh
git reset --hard // 回撤git stash pop 内容
```

#### 回退命令

``` js
git reset --hard commitId  // 回退到指定提交，
```

#### 远程仓库

``` js
git remote -v // 查看远程仓库
git remote add <remote-name> git地址 // 添加远程仓库
git remote rename [old] [new]    // 修改远程仓库名
git remote remove [name]   // 删除远程仓库
git pull 远程仓库名 [远程分支:本地分支]  // 拉取最新代码到本地 是 git fetch + git merge
git branch --set-upstream-to=origin/<branch> master // 将远程分支与本地分支建立关联
```
#### 合并命令

``` js
git merge 分支名 // 将分支合并到当前分支
git rebase -i HEAD~3 // 变基，合并多条commit为一条
```

#### git常见问题
```
1、fatal: refusing to merge unrelated histories

解决方案：git pull –-allow-unrelated-histories
```



