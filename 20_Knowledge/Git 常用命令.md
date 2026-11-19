### 1. 仓库初始化与配置

|**命令**|**功能说明**|
|---|---|
|`git init`|在当前目录初始化新的本地 Git 仓库|
|`git clone <url>`|克隆远程仓库到本地|
|`git config --global user.name "<name>"`|设置全局提交用户名|
|`git config --global user.email "<email>"`|设置全局提交邮箱|

### 2. 日常修改与提交

|**命令**|**功能说明**|
|---|---|
|`git status`|查看工作区与暂存区的文件状态|
|`git diff`|查看工作区与暂存区的具体代码差异|
|`git add <file>` / `git add .`|将指定文件 / 所有改动添加到暂存区|
|`git commit -m "<msg>"`|将暂存区内容提交到本地仓库并附带说明|
|`git commit --amend`|修改最近一次提交的说明或补充漏掉的文件|

### 3. 分支管理与合并

|**命令**|**功能说明**|
|---|---|
|`git branch`|查看本地分支（加 `-a` 查看包含远程的所有分支）|
|`git switch -c <branch>`|创建并切换到新分支（等价于 `git checkout -b`）|
|`git switch <branch>`|切换到指定已有分支|
|`git merge <branch>`|将指定分支合并到当前所在分支|
|`git rebase <branch>`|将当前分支的提交变基到目标分支最新提交之上|
|`git branch -d <branch>`|删除已合并的本地分支（未合并用 `-D` 强制删除）|

### 4. 远程仓库与同步

|**命令**|**功能说明**|
|---|---|
|`git remote -v`|查看已关联的所有远程仓库别名及地址|
|`git remote add <name> <url>`|添加新的远程仓库关联|
|`git fetch <remote>`|拉取远程仓库最新元数据与分支，但不自动合并|
|`git pull <remote> <branch>`|拉取远程分支更新并合并到当前分支|
|`git push <remote> <branch>`|将本地分支推送到指定远程仓库|
|`git push -u <remote> <branch>`|首次推送并建立本地与远程分支的默认追踪关系|

### 5. 撤销、回退与暂存现场

|**命令**|**功能说明**|
|---|---|
|`git restore <file>`|丢弃工作区中指定文件的未暂存修改|
|`git restore --staged <file>`|将文件从暂存区撤回工作区（保留文件内容修改）|
|`git reset --soft HEAD~1`|撤销最近一次提交，保留改动在暂存区|
|`git reset --hard <commit_id>`|彻底回退到指定提交版本（清空未提交改动）|
|`git revert <commit_id>`|生成一个反向提交来安全撤销某次历史提交|
|`git stash` / `git stash pop`|临时储藏当前未提交的工作现场 / 恢复最近储藏|

### 6. 历史记录与排查

|**命令**|**功能说明**|
|---|---|
|`git log --oneline --graph --all`|以精简图形化方式查看所有分支的提交历史|
|`git show <commit_id>`|查看某次提交的详细信息及改动内容|
|`git blame <file>`|逐行查看文件的最后修改者及对应提交记录|

### 7. 关闭 `core.quotepath`

```bash
git config --global core.quotepath false
```