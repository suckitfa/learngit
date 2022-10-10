# Git intro note
Git is a version control system.
Git is free software.
Git is a free software distributed under the
### 廖雪峰的git教程笔记
以下命令都必须在当前的git文件夹中运行
1. 使用`git add <file>`,注意可以多次使用，添加多个文件。
2. 使用命令`git commit -m <message>` 提交`git add`追踪的变化。

- `git status` 随时展示当前工作区的状态
- `git diff`查看文件修改内容


### HEAD指针表示当前版本
- `git reset --hard commit_id` 可以切换历史版本的代码
-`git reflog`记录了每一次的命令

### 暂存区 stage 的概念
- 第一步是用git add把文件添加进去，实际上就是把文件修改添加到暂存区；

- 第二步是用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。

### git的优点
- 保存文件的修改, 所以在这里git提交的数据都是某个文件的修改！！！

### 常用命令
- `git add <file_name> `将文件中工作区（work space）的修改放到暂存区stage里面
- `git commit -m "some message"` 提交到版本库 repository
- `git checkout -- <file_name>` 丢去文件中工作区的修改: 就是让这个文件回到最近一次git commit或git add时的状态。
- `git reset HEAD <file>` 将暂存区的(unstage)撤销掉,重新放回工作区