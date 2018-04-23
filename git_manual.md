	git相关
	1.SVN是集中式的版本控制工具，集中式版本控制工具是需要联网的，Git是分布式的版本控制工具，分布式版本控制工具是不需要联网的。
	2.常用的git命令
	   
	   查看相关：
	   git version									查看git版本
	   git status									查看当前分支的状态
	   cat [文件名]									打开文件
	   pwd										可以显示当前目录的路径
	   ls -ah										可以查看当前目录下的所有文件，包括隐藏
	   git diff										可以查看修改记录
	   git log										显示最近到最远的提交日志
	   
	
	   分支相关：
	    git merge [分支名]							将指定分支合并到当前分支
	    git branch	[新建分支名]						创建一个新的分支
	    git checkout [分支名]							切换到指定分支
	    git checkout -b [新建分支名]					创建并切换到指定分支
	    git branch -d [删除分支名]						如果当前分支未被合并，会提示
	    git branch -D [删除分支名]						彻底删除分支
	
	    配置相关：
	
	    git config --global color.ui true					配置颜色
	    cd ~/.ssh									   查看是否有ssh key,如果没有，不会有该文件夹
	    ssh-keygen -t rsa -C "邮箱"						   生成密钥并设置密码
	    git config --global user.name "用户名"			配置用户名
	    git config --global user.email "邮箱"				配置邮箱
	    git config --global credential.helper store			配置不用每次都输入用户名密码
	
	
	   查看远程仓库状态：
	   git remote 									查看远程仓库分支名
	   git remote -v								查看远程仓库地址及权限
	
	  本地仓库操作：
	
	   git init									把当前目录变成可以管理的本地仓库
	   
	   git add     [文件名]							添加文件到本地暂存区
	   git add .								一次性添加所有改动到暂存区
	   git add -A								一次性添加所有改动到暂存区
	   git commit -m "提交描述"					将所有本地暂存区提交到本地仓库
	
	    
	
	  远程仓库操作
	    git remote add origin git@github.com:ThemeLove/HelloGit.git 	关联远程仓库，只有关联才			          能push代码	 
	    git push -u [远程仓库分支] [本地仓库分支]			第一次推送所有内容到远程仓库
	    git clone  git@github.com:ThemeLove/HelloGit.git	克隆远程库，有ssh协议和Https协议
	    git push [远程仓库分支] [本地仓库分支]			将指定本地仓库分支提交到远程仓库
	    git pull	[远程仓库分支] [本地仓库分支]				从远程库更新最新代码
	    git pull [远程仓库分支] [本地仓库分支]	--allow-unrelated-histories	如果merge出错，用这个命令	
	
	
	   编辑文件：
	   vi [文件路径]			
	1：以编辑模式打开文件
	2：修改完后按ESC键退出编辑模式
	3：输入：wq退出并保存
	   cat [文件路径] :查看文件内容
	
	
	
	
	
	pull的时候会提示Please enter a commit message to explain why this merge is necesary.......
	解决办法：
	1.按键盘字母 i 进入insert模式
	2.修改最上面那行黄色合并信息,可以不修改
	3.按键盘左上角"Esc"
	4.输入":wq",注意是冒号+wq,按回车键即可
	
	
	.gitignore的配置文件：
	对于已经在追踪的文件，在配置文件中配置忽略，不会起作用，需要将其目录删除重新配置
	
	
	git log --graph --pretty=oneline --abbrev-commit     可以查看分支的合并情况
	
	准备合并dev分支，请注意--no-ff参数，表示禁用Fast forward：
	git merge --no-ff -m "merge with no-ff" dev
	git merge [分支]  		
