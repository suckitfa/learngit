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