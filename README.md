(1)初始化一个仓库
	git init
(2)添加文件到仓库
	git add <file1,file2,...>
	git commit -m <message>
(3)查看工作区状态
	git status
(4)查看文件修改情况
	git diff <file>
(5)版本穿梭
	git reset --hard <commit_id>	特殊地，HEAD^,HEAD^^,...
(6)查看版本历史
	git log
(7)查看命令历史
	git reflog
(8)丢弃工作区的修改,回到最近一次git commit或git add时的状态
	git checkout -- <file>
(9)将文件撤出暂存区
	git reset HEAD <file>
(10)从版本库中删除文件
	git rm <file>(若本地已经先删除文件，也可用git add <file>)
	git commit -m <message>
(11)创建SSH Key
	ssh-keygen -t rsa -C "<email>"
(12)添加远程库
	关联根据github命令来就行，之后使用git push -u origin master来更新
(13)克隆远程库
	先建立github代码仓库，然后使用git clone git@github.com:qymeng/<仓库名>.git
