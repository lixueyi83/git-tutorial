<Open README.md with vim or gedit>
# git-tutorial
########################################################################################################################
##						 tutorial 1  							      ##
########################################################################################################################

http://www.jianshu.com/p/97946d9df5bd 
Git命令大全（Github）

CREAT(创建)
===========

git init                                      在当前目录下创建一个本(Create a new local repository)
git clone  ssh://user@domain.tld/repo.git     在远程库克隆一个本地库(Clone an existing repository)


Configuration(配置)
===================

git config [--global] user.name       	设置提交时附带的名字(Set the name attached to all your commits)
git config [--global] user.email        设置提交时附带的email(Set the email attached to all your commits)
git config --global color.ui auto       设置命令行输出回执的颜色(Set colorzition of  command line output for all repos)
git config [--global] user.name         获取当前库设置的用户名(Print set name(in current repository or globally))
git config [--global] user.email        获取当前库设置的email(Print set email(in current repository or  globally))


Local Changes(本地操作)
=======================

git status    	查看工作区内的文件修改(List changed files in your working directory)
git diff       	查看已追踪文件的修改(List changed to tracked files)
git add       	添加此文件的所有修改在下次提交时(Add all current changed in file to the next commit)
git add .     	添加本地库中的所有修改在下次提交的时(Add all current changed to the next commit)
git mv          修改文件名并添加到下次提交当中(Rename file and add it to next commit)
git rm          删除此文件并将此处删除添加到下次提交当中(Delete file and add its deletion to next commit)    
git commit -a   提交工作区所有文件(Commit all local changes in tracked files)


Commit History(提交历史)
========================

git log                                 显示所有的提交日志(Show all commits)
git log -p                              这个文件的最后一次提交日志(Shwo changes over time for a specific file)
git log --author=<committer name>  	这个提交者最后一次的提交日志(Show changes over time for a specific committer)
git blame <file>                        此文件被谁修改了(Who changed what and when in file)
git stash                               查看临时的文件变动 (Store changes temporarily)
git stash pop                           删除上一次记录储蓄新的改动记录(Remove and apply changes)
git rm --cached <file>                  把此文件从过去的提交记录中删除但是保留当前本地的文件(Remvoe file from previous commits but keep it locally)


Branches & Tags(分支和标签)
===========================

git branch                              	本地所有的分支列表(List all existing branches)
git checkout <branch>            		切换分支(Switch HEAD branch)
git branch <new branch>        			创建新分支(Creat a new branch based on your current HEAD)
git branch --track <new-branch><remote-branch>  创建一个新的分支基于一个远程的分支(Creat a new  tracking branch based on a remote branch)
git branch -d <branch>                          删除一个本地分支(Delete a local branch)
git branch origin --delete <branch>       	删除一个远程分支(Delete a remote branch)
git push <remote> : <old name>     		重命名远程分支名(Rename a branch on remote)git push
git push <remote> <new name>           
git tag <tag-name>       			给当前提交打一个tag,也可以查看当前标签(Tag the current commit)


Update & Publish(更新和提交)
============================

git remote -v                         		查看远程库的地址列表(List all currently configured remotes)
git remote show <remote>       			查看这个远程库的信息(Show information about a remote)
git remote add <remote> <url> 			添加新的远程库(Add new remote repository)
git remote rename <old-name> <new-name>    	重命名远程库(Rename a remote)
git fetch <remote>       			从远程库更新所有的信息到本地，但是不合并(Download all changes from remote,but don't merge into HEAD)
git fetch -p <remote>     			从远程库更新所有的信息到本地，但不合并并清理已删除的远程分支(Download all changes fromm remote,but don't merge in HEAD and clean up deleted branchs from origin)
git pull <remote><branch>   			从远程库更新数据并立即合并数据(Download changes and directly merge into HEAD)
git push <remote><branch>   			将本地数据同步到远程库中(Publish local changes on a remote)
git remote add --track <remote-branch><remote><url>  	追踪一个远程库(Track a remote repository)
git push --tags                         		同步标签到远程库(Publish your tags
git remote show <remote>      				显示远程库信息(Show information about a submodule)


Merge & Rebase(分支合并和重整数据)
=================================

git merge <branch>       	将其他分支和并到当前分支(Merge branch into your current HEAD)
git rebase <branch>          	将亲她分支合并到当前分支并按照提交顺序排序(Rebase your current HEAD onto branch)
git rebase --abort             	终止当前合并(Abort a rebase)
git rebase --continue       	解决冲突后继续当前合并和重整(Continue a rebase after resolving confilcys)
git mergetool                   使用配置的合并工具解决冲突(Resolve conflicts using your configured merge tool)
git add <resolved-file>     	手动解决冲突使用编辑器并标记已解决的文件
git rm <resolved-file>


Undo(撤销)
==========

git reset --hard HEAD            丢弃所有的本地修改(Discard all local changes in your working directory)
git checkout HEAD <file>         丢弃此文件的本地修改(Discard local changes in a specific file)
git revert  <commit>             撤销某次的提交内容(Revert a commit by providing a new commit with contrary changes)
git checkout <commit><file>    	 撤销某次提交的某个文件的内容(Revert a specific file from a previous commit)


重置头指针到过去的某个提交上,版本回退(Reset your HEAD pointer to a previous commit)
=================================================================================

git reset --hard  <commit>     		回退到某个版本(Discarding local changes)
git reset <commit>                   	回退到某个版本并保存未追踪的改动
git reset --keep <commit>       	回退到某个版本并保存未提交的改动



########################################################################################################################
##						 tutorial 2 							      ##
########################################################################################################################
git init                                                  # 初始化本地git仓库（创建新仓库）
git config --global user.name "xxx"                       # 配置用户名
git config --global user.email "xxx@xxx.com"              # 配置邮件
git config --global color.ui true                         # git status等命令自动着色
git config --global color.status auto
git config --global color.diff auto
git config --global color.branch auto
git config --global color.interactive auto
git config --global --unset http.proxy                    # remove  proxy configuration on git
git clone git+ssh://git@192.168.53.168/VT.git             # clone远程仓库
git status                                                # 查看当前版本状态（是否修改）
git add xyz                                               # 添加xyz文件至index
git add .                                                 # 增加当前子目录下所有更改过的文件至index
git commit -m 'xxx'                                       # 提交
git commit --amend -m 'xxx'                               # 合并上一次提交（用于反复修改）
git commit -am 'xxx'                                      # 将add和commit合为一步
git rm xxx                                                # 删除index中的文件
git rm -r *                                               # 递归删除
git log                                                   # 显示提交日志
git log -1                                                # 显示1行日志 -n为n行
git log -5
git log --stat                                            # 显示提交日志及相关变动文件
git log -p -m
git show dfb02e6e4f2f7b573337763e5c0013802e392818         # 显示某个提交的详细内容
git show dfb02                                            # 可只用commitid的前几位
git show HEAD                                             # 显示HEAD提交日志
git show HEAD^                                            # 显示HEAD的父（上一个版本）的提交日志 ^^为上两个版本 ^5为上5个版本
git tag                                                   # 显示已存在的tag
git tag -a v2.0 -m 'xxx'                                  # 增加v2.0的tag
git show v2.0                                             # 显示v2.0的日志及详细内容
git log v2.0                                              # 显示v2.0的日志
git diff                                                  # 显示所有未添加至index的变更
git diff --cached                                         # 显示所有已添加index但还未commit的变更
git diff HEAD^                                            # 比较与上一个版本的差异
git diff HEAD -- ./lib                                    # 比较与HEAD版本lib目录的差异
git diff origin/master..master                            # 比较远程分支master上有本地分支master上没有的
git diff origin/master..master --stat                     # 只显示差异的文件，不显示具体内容
git remote add origin git+ssh://git@192.168.53.168/VT.git # 增加远程定义（用于push/pull/fetch）
git branch                                                # 显示本地分支
git branch --contains 50089                               # 显示包含提交50089的分支
git branch -a                                             # 显示所有分支
git branch -r                                             # 显示所有原创分支
git branch --merged                                       # 显示所有已合并到当前分支的分支
git branch --no-merged                                    # 显示所有未合并到当前分支的分支
git branch -m master master_copy                          # 本地分支改名
git checkout -b master_copy                               # 从当前分支创建新分支master_copy并检出
git checkout -b master master_copy                        # 上面的完整版
git checkout features/performance                         # 检出已存在的features/performance分支
git checkout --track hotfixes/BJVEP933                    # 检出远程分支hotfixes/BJVEP933并创建本地跟踪分支
git checkout v2.0                                         # 检出版本v2.0
git checkout -b devel origin/develop                      # 从远程分支develop创建新本地分支devel并检出
git checkout -- README                                    # 检出head版本的README文件（可用于修改错误回退）
git merge origin/master                                   # 合并远程master分支至当前分支
git cherry-pick ff44785404a8e                             # 合并提交ff44785404a8e的修改
git push origin master                                    # 将当前分支push到远程master分支
git push origin :hotfixes/BJVEP933                        # 删除远程仓库的hotfixes/BJVEP933分支
git push --tags                                           # 把所有tag推送到远程仓库
git fetch                                                 # 获取所有远程分支（不更新本地分支，另需merge）
git fetch --prune                                         # 获取所有原创分支并清除服务器上已删掉的分支
git pull origin master                                    # 获取远程分支master并merge到当前分支
git mv README README2                                     # 重命名文件README为README2
git reset --hard HEAD                                     # 将当前版本重置为HEAD（通常用于merge失败回退）
git rebase
git branch -d hotfixes/BJVEP933                           # 删除分支hotfixes/BJVEP933（本分支修改已合并到其他分支）
git branch -D hotfixes/BJVEP933                           # 强制删除分支hotfixes/BJVEP933
git ls-files                                              # 列出git index包含的文件
git show-branch                                           # 图示当前分支历史
git show-branch --all                                     # 图示所有分支历史
git whatchanged                                           # 显示提交历史对应的文件修改
git revert dfb02e6e4f2f7b573337763e5c0013802e392818       # 撤销提交dfb02e6e4f2f7b573337763e5c0013802e392818
git ls-tree HEAD                                          # 内部命令：显示某个git对象
git rev-parse v2.0                                        # 内部命令：显示某个ref对于的SHA1 HASH
git reflog                                                # 显示所有提交，包括孤立节点
git show HEAD@{5}
git show master@{yesterday}                               # 显示master分支昨天的状态
git log --pretty=format:'%h %s' --graph                   # 图示提交日志
git show HEAD~3
git show -s --pretty=raw 2be7fcb476
git stash                                                 # 暂存当前修改，将所有至为HEAD状态
git stash list                                            # 查看所有暂存
git stash show -p stash@{0}                               # 参考第一次暂存
git stash apply stash@{0}                                 # 应用第一次暂存
git grep "delete from"                                    # 文件中搜索文本“delete from”
git grep -e '#define' --and -e SORT_DIRENT
git gc
git fsck

