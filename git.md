# Git 版本控制工具的使用

## 仅本地使用

---

- `配置git`：

git config --global user.name "your_name"

git config --global user.email "your_email"

- `创建项目`：

在电脑上创建一个文件夹，然后对这个文件夹进行版本控制。

创建.gitignore文件，添加：

```python
__pycache__/          # 忽略__pycache__文件夹下的所有自动生成的文件，可以避免项目混乱
```

- `初始化仓库`

在pycharm中打开终端：

git init

- `查看状态`

git status

显示：未添加进仓库或未提交的所有文件

- `添加进仓库`

git add .

添加所有文件

- `提交`

第一次提交: git commit -m "describle_message"

修改某些文件后提交： git commit -am "describle_message"

增加某些文件后提交:

git add .

git commit -m "describle_message"

- `提交历史`

git log

打印详细的提交记录。

git log --pretty=oneline

只打印 ID 和 message 。

- `撤销`

git checkout .

让项目恢复到最后一次提交后的状态。

- `检出`

在真正reset之前看一看，要回退的版本是什么样子的。（个人理解）

可以检出历史提交中的任何一次。

`git checkout ID的前6个字符`

此时，指针进入分离头指针状态。

当指针回到master时

指令：`git checkout master`

版本回退效果消失。等同于`预览回退效果`。

- `重置`

git reset --hard ID的前6个字符

- `正常`

git status

提示： working tree clean.

- `删除`

删除仓库后，所有的历史版本将消失。删除.git文件即删除了仓库。

rm -rf .git

- `理念`

确保每一次提交前的版本都是可运行的。

工作树的流程。

添加：并非提交，而是让git关注这些文件。以供git去track（追踪）。

分支是项目的一个版本。

提交：相当于一个特定时间点的快照。

## 与远程仓库交互

---

[补充学习视频: 《git 精简教程》](https://www.bilibili.com/video/BV1ky4y1M7HC/?spm_id_from=333.999.0.0&vd_source=a91d4e34f00c82dd22591a1b4c0ad245)

学习笔记：

以下命令都是在pycharm终端运行的。

- `git status`

查看当前文件夹与git的关系。

- `ls -Hidden`

查看隐藏文件。

- `git rm --cached filename`

将文件从暂存区撤出来。

- `git diff filename`

将暂存区(+)和本地内容进行对比

- `git diff --cached`

将仓库和暂存区内容进行对比。

`git diff` 还可以对不同分支进行比对。

`git -rm filename` `git commit -m "del filename"` 可以实现本地和仓库都删除该文件，而不必经过暂存区。

---

- 远程仓库

- `git pull`

拉取远程代码

- `git push remote_branch local_branch`

将自己的代码推送到远程仓库

- `git branch`

查看所有分支

- `git branch -a`

同时查看远程分支

- `git branch new_branch`

创建本地新分支

- `git checkout -b new_branch`

创建本地新分支并切换

- `git checkout new_branch`

切换到已有分支

- `git checkout -d new_branch`

删除分支

- `git push --ser-upstream origin new_branch`

新建的分支需要和远程分支对应。

- `git tag tag_name`

本地打标签。

- `git tag tag_name ID`

给不同ID打标签

还可以制定一些messages

- `tag` 作用

不修改，面向交付，对单个commit的快照。

而branch:

修改，面向开发，对多个commit的快照。

---

- `为主机配置SSH，连接github`

目的：push时不必输入密码。

`环境`：

windows10 + git bash

- 查看本地主机是否已存在ssh key

`cd ~/.ssh`

实际上等同于`cd C:/Users/AMY/.ssh`

`ls`

若存在id_rsa, id_rsa.pub，则说明存在ssh key。

若不存在，先生成。

`ssh-keygen -t rsa -C "xxx@xxx.com"` # 执行后一直回车

- 获取公钥内容

`cat id_rsa.pub`

复制

- 添加进github上

settings < SSH and GPG keys < New SSH key < 取名，粘贴

- 验证

`ssh -T git@github.com`

出现successful即成功。

---

 ## 在IDE中使用git bash终端

win10 环境

1. 下载Git

2. 在pycharm中settings < tools < terminal : 修改powershell path

3. 在vscode中直接点击终端，加号旁边有个倒小于号，点击切换到bash终端即可。
