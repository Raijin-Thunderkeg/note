# git参考指南
### git基本命令

1. 从远端仓库克隆到本地
```
git clone https://github.com/Raijin-Thunderkeg/note.git
```

2. 添加与提交

- 把改动添加到缓存区
```
git add <filename>
git add .
```
- 提交改动到本地

```
git commit -m '代码的提交信息'
```

3. 推送改动

- 将改动提交到远端仓库

```
git push origin master
```
master 可以换成其他分支

4. 分支

- 创建一个叫'note'的分支,并切换

```
git checkout -b note
```
- 切换分支

```
git checkout master
```
master 可以换成其他分支名
- 删除分支

```
git branch -d note
```
- 删除git远端分支

```
git push origin --dlelte note
```

5. 更新与合并

- 更新本地仓库到最新版本

```
git pull
```
- 合并其他分支到当前分支

```
git merge <branch>
```

- 比较两个分支的不同

```
git diff <source_branch> <target_branch>
```

6. 标签

- 创建标签

```
git tag -a <v1.0.0.0> -m <注解>
```
- 查看提交的日志记录

```
git log
```

- 删除标签

```
git tag -d v1.0.0.0
```
- 删除git远端tag

```
git push origin --delete tag v1.0.0.0
```

7. 替换本地改动

- 用HEAD中的最新内容替换工作目录中的文件,加到缓存区以及新文件不受影响
```
git checkout -- <filename>
```
- 假如你想要丢弃你所有的本地改动与提交，可以到服务器上获取最新的版本并将你本地主分支指向到它

```
git fetch origin
git reset --hard origin/master
```

8. 缓存机制
- 缓存本地修改的代码

```
git stash
```
- 查看缓存片段

```
git stash list
```
- 还原缓存片段

```
git stash apply stash@{0}
```



