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

### 工作区(work space)和版本库，以及版本库（repository）中的暂存区 stage 的概念
- 第一步是用git add把文件添加进去，实际上就是把文件修改添加到暂存区；

- 第二步是用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。

### git的优点
- 保存文件的修改, 所以在这里git提交的数据都是某个文件的修改！！！

### 常用命令
- `git add <file_name> `将文件中工作区（work space）的修改放到暂存区stage里面
- `git commit -m "some message"` 提交到版本库 repository
- `git checkout -- <file_name>` 丢去文件中工作区的修改: 就是让这个文件回到最近一次git commit或git add时的状态。(会影响文件的内容的)
- `git reset HEAD <file>` 将暂存区的(unstage)撤销掉,重新放回工作区

#### git checkout -- <file_name> 和 git reset HEAD的场景

- 场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。
- 场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
- 场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

### 远程仓库的配置
```sh
# 输入下面命令生成秘钥
ssh-keygen -t rsa -C "254202042@qq.com"
# 将生成的秘钥加入github页面
```

### 远程仓库增加，第一次提交，与删除
```sh
git remote add origin <git_repo_url>
git remote add origin git@server-name:path/repo-name.git

# 第一次推送master分支的所有内容
git push -u origin master 

# 删除本地仓库和远程仓库的关系
git remote rm origin
删除”其实是解除了本地和远程的绑定关系，并不是物理上删除了远程库。远程库本身并没有任何改动。要真正删除远程库，需要登录到GitHub，在后台页面找到删除按钮再删除。
```

### Git分支（branch）的管理
- 分支管理的还是原来文件的修改！！
- 现在有了分支，就不用怕了。你创建了一个属于你自己的分支，别人看不到，还继续在原来的分支上正常工作，而你在自己的分支上干活，想提交就提交，直到开发完毕后，再一次性合并到原来的分支上，这样，既安全，又不影响别人工作。
```ssh
# 查看git分支
git branch
# 创建分支
git branch <branch_name>
# 切换分支 两个命令
git checkout <branch_name> 
# - 注意区分 git checkout -- <file_name>
git switch -c <branch_name>

# 分支合并
git merge <branch_name>

# 删除分支 
git branch -d <branch_name>
```
测试分支feature1
### 如何自己搭建内部的git服务器
- 另一个办法是自己动手，搭一个Git服务器，因为是你自己的Git服务器，所以别人也是看不见的。这个方法我们后面会讲到的，相当简单，公司内部开发必备。
