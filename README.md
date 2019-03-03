学习使用Git
==========
(1)在当前目录初始化一个仓库
-------------------------
>git init
(2)添加文件到仓库
-------------------------
>git add <file1,file2,...>
>git commit -m <message>
(3)查看工作区状态
-------------------------
>git status
(4)查看文件修改情况
-------------------------
>git diff <file>
(5)版本穿梭
-------------------------
>git reset --hard <commit_id>	特殊地，HEAD^,HEAD^^,...
(6)查看版本历史
-------------------------
>git log
(7)查看命令历史
-------------------------
>git reflog
(8)丢弃工作区的修改,回到最近一次git commit或git add时的状态
-------------------------
>git checkout -- <file>
(9)将文件撤出暂存区
-------------------------
>git reset HEAD <file>
(10)从版本库中删除文件
-------------------------
>git rm <file>(若本地已经先删除文件，也可用git add <file>)
>git commit -m <message>
(11)创建SSH Key
-------------------------
>ssh-keygen -t rsa -C "<email>"
(12)添加远程库
-------------------------
>关联根据github命令来就行，之后使用git push -u origin master来更新
(13)克隆远程库
-------------------------
>先建github代码仓库，然后使用git clone git@github.com:qymeng/<仓库名>.git
(14)创建与合并分支
-------------------------
>查看分支：	git branch，有 * 的为当前分支
>创建分支：	git branch <name>
>切换分支：	git checkout <name>
>创建并且切换分支：	git branch -b <name>
>合并分支到当前分支:	git merge <name>
>删除分支：	git branch -d <name>
(15)解决冲突
-------------------------
>在不同分支上对同一文件修改后要合并分支，需要先解决冲突
>git log --graph --pretty=oneline --abbrev-commit
(16)分支管理策略
-------------------------
>日常团队开发中，合并分支使用 --no-ff 参数使用普通模式合并分支。
(17)bug修复
-------------------------
>日常是我们在自己的分支上开发，某次正在开发时有人发现master上的bug，需要我们来修改。
	* 1.使用git stash来保存当前分支的工作现场
	* 2.切换到要bug的master分支，然后新建临时bug修复分支issue-xx
	* 3.在issue-xx分支上修改完后合并到master上
	* 4.删除临时分支issue-xx
	* 5.切换回我们之前在进行开发的分支，使用git stash list来查看工作现场保存情况
	* 6.恢复工作现场：一种是git stash apply + git stash drop；或者git stash pop
(18)新功能(Feature)开发
-------------------------
>舍弃新功能开发分支，这个分支是一个没有被合并过的分支，使用强行删除git branch -D <name>
(19)多人协作
-------------------------
	查看远程库信息：	git remote -v
	从本地推送分支：	git push origin <branch-name>
	如果推送失败：		先使用git pull抓取远程的新提交来解决冲突
	克隆仓库：			使用git clone来克隆远程库
	建立要和远程分支对应的本地分支：git checkout -b branch-name origin/branch-name
	建立本地分支和远程分支的关联：	git branch --set-upstream branch-name origin/branch-name
	从远程抓取分支：	git pull
(20)标签管理
-------------------------
	标签(tag)和某个commit绑定。
	新建标签：		git tag <tag-name> [commit-id，默认HEAD]
	指定标签信息:	git tag -a <tag-name> -m "message"
	查看所有标签：	git tag
	查看标签对应的版本信息：	git show <tag-name>
	推送本地标签：	git push origin <tag-name>
	推送全部标签：	git push origin --tags
	删除本地标签：	git tag -d <tagname>
	删除一个远程标签：	git push origin :refs/tags/<tagname>	