##git branch	分支
		git branch 											查看本地所有分支，并用*标记当前分支
		git branch [branch-name]							创建分支
		git checkout [branch-name]							切换分支
		git checkout -b [branch-name]						创建并切换分支
		git branch -d [branch-name]							删除指定分支，如果当前分支未合并，会提示
		git branch -D [branch-name]							强制删除分支，无论是否已被合并
		git branch -v										查看各个分支最后一次提交信息
		git merge [branch-name]								合并指定分支到当前分支  
		git merge --no-ff -m "merge with no-ff" [branch-name] 合并指定分支到当前分支，禁用Fast forward         
		git branch --merged									查看已合并到当前的分支
		git branch --no--merged								查看尚未合并到当前分支的分支
		git push [远程仓库]	[本地分支]：[远程分支名]			将本地分支推送到远程指定仓库指定分支
		git checkout -b [本地分支名] [远程仓库名]/[远程分支名]  创建本地分支并跟踪指定远程仓库下指定分支
		git pull [远程分支] [本地分支]:[远程分支名]				拉取指定远程仓库下指定分支到指定本地分支
		git checkout --track [远程仓库]/[远程分支]			在本地创建与远程分支同名的分支，并追踪远程分支 
		git branch -r										查看远程分支
		git branch -a										查看所有分支：当前分支和远程分支

		删除远程仓库分支
		git push 远程仓库 --delete 远程分支
	    eg: 删除远程origin仓库的 testbranch分支
	    git push origin --delete testbranch


​		
​		

