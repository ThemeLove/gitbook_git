###git	
SVN是集中式的版本控制工具，集中式版本控制工具是需要联网的；  
Git是分布式的版本控制工具，分布式版本控制工具是不需要联网的。    

学习git一定要理解几个重要的概念  

**远程仓库:remote Repository    
本地仓库:local Repository    
工作区:	worksapce    
暂存区： git add  时会把文件提交到索引库（建立索引） 和 暂存区   
堆：git stash 时会把暂存区和工作区已经追踪文件的改动保存到堆中，保存当前工作进度**

![](/images/git_overview.png)  


###git 相关链接  
[廖雪峰git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000 "廖雪峰git教程")   
[git详解之一](http://blog.jobbole.com/25775/ "git详解之一")  
[git详解之二](http://blog.jobbole.com/25808/ "git详解之二")  
[git详解之三](http://blog.jobbole.com/25877/ "git详解之三")      




##常用的git命令

####git 使用技巧和窍门  
	1.输入git命令的时候可以敲两次Tab键，就会列出所有匹配的可用的命名建议  
	  比如：输入git co 后按两次Tab键会列出 commit config,根据提示完成命令   
	2.查看命令帮助：当你不熟悉git的某个命令时，可以用如下命令进行查看帮助  
	  git command -help  : 命令行模式下查看   
	  git command --help : 新开浏览器查看帮助   

####查看相关：
	   git version									查看git版本
	   git status									查看当前分支的状态
	   cat [文件名]								  打开文件
	   pwd										    可以显示当前目录的路径
	   ls -ah										可以查看当前目录下的所有文件，包括隐藏
	   git diff										比较工作目录中当前文件和暂存区域快照之间的差异，也就是修改之后没有暂存起													来的内容  
	   git diff --cached							比较已经惨存起来的文件和上次提交时快照之间的差异
		
	   git log										显示最近到最远的提交日志
	   git log -n 									查看最近n条提交记录
	   git log -p									查看提交记录并展示每次提交的内容差异
	   git log --stat								显示提交记录的简要的增改行数统计
	   git log --pretty=oneline						一行显示提交记录         
	   git reflog 	 								是显示所有的操作记录，包括提交，回退的操作，  
													一般用来找出操作记录中的版本号，进行回退

####配置相关：
	    cd ~/.ssh									   		查看是否有ssh key,如果没有，不会有该文件夹
	    ssh-keygen -t rsa -C "邮箱"						    生成密钥并设置密码
	    git config --global user.name [用户名]				配置用户名
	    git config --global user.email [邮箱]				配置邮箱
		git config user.name  								直接查看用户名配置
		git config --global core.editor [编辑器]				配置编辑器
		git config --global merge.tod [差异分析工具]			配置差异分析工具
	    git config --global color.ui true					配置颜色
	    git config --global credential.helper store			配置不用每次都输入用户名密码
		git config --list									查看已有的配置信息

####本地仓库操作：
	   git init									把当前目录变成可以管理的本地仓库
	   git init	[project-name]					在当前目录下project-name目录，变成可以管理的本地仓库，如果没有改目录则创建 
	   git status								查看当前工作目录的状态
	   git add [文件名]						  添加文件到本地暂存区
	   git checkout [文件名]				      抛弃文件修改的命令，回到上次提交的状态  
	   git checkout .							本地所有没有提交的修改都回到原来的状态
	   git add .								一次性添加所有改动到暂存区
	   git add -A								一次性添加所有改动到暂存区
	   git commit -m "提交描述"					 将所有本地暂存区提交到本地仓库
	   git commit -a -m "提交描述"				 先add再commit 
	   git commit --amend -m "提交描述"			 追加到上次提交
	   git rm [file]							从工作目录中删除并且从暂存区移除  
	   git rm --cached [file]    				从暂存区移除但不从工作目录中移除  
	   git rm -r --cached [file]				对已经进行版本追踪的文件进行移除  
	   git reset HEAD [file]					将file从暂存区移除  
	   git reset --hard <commit_id>				回到指定commit_id时的提交，文件内容都会回退
	   git rm \*~								删除当前目录及其子目录中所有~结尾的文件  
	   git mv [old-file] [new-file]				重命名文件  
	   git rebase [branch-name]					分支的衍合 
	   git stash								命令的作用就是将目前还不想提交的但是已经修改的内容进行保存至堆栈中，  
												后续可以在某个分支上恢复出堆栈中的内容。
	   
	
####查看远程仓库状态：
	   git remote 									查看远程仓库分支名
	   git remote -v								查看远程仓库地址及权限	    
	
####远程仓库操作
		

```bash
#
git clone [远程库地址，有ssh协议和Https协议2种]	 [projet-name]		
#克隆远程库，有ssh协议和Https协议,到本地project-name目录下  
 例如：git clone  git@github.com:ThemeLove/HelloGit.git	
git remote add [为远程仓库指定的仓库名] [远程仓库地址，有ssh协议和Https协议2种]      关联远程仓库，只有关联才能push代码  
	例如：git remote add origin git@github.com:ThemeLove/HelloGit.git  
git remote show [远程仓库名]							显示远程仓库详细信息	
git remote rename [old 远程仓库名] [new 远程仓库名]	重名名远程仓库名
git remote set-url origin 远程仓库url					重新设置远程仓库地址
git remote rm [远程仓库名]							删除指定远程仓库

git push -u [远程仓库] [本地仓库分支]				第一次推送所有内容到远程仓库
git push [远程仓库] [本地分支]：[远程分支]			将本地仓库分支推送到远程仓库下的远程分支
git push [远程仓库] [本地分支]					将本地仓库分支推送到远程仓库下的同名分支 
git push -f [远程仓库] [本地分支]：[远程分支] 	 强制推送本地分支到远程仓库指定分支

git pull [远程仓库] [本地分支]：[远程分支]			从远程仓库下的远程分支更新最新代码到本地分支，并主动合并  
git pull [远程仓库] [本地分支]					从远程仓库下的同名分支更新代码到本地分支，并主动合并  
git pull [远程仓库] [本地分支]：[远程分支] --allow-unrelated-histories	如果merge出错，用这个命令

git fetch [远程仓库] [本地分支]：[远程分支]			从远程仓库下的远程分支更新代码到本地分支，不主动合并  
git fetch [远程仓库] [本地分支]					从远程仓库下的同名分支更新代码到本地分支，不主动合并		
```
###git help
		git help			帮助选项
		git --help			帮助选项
		git help [git 命令] 	查看git命令帮助,会打开浏览器显示该命令的使用帮助，是本地git安装目录里的html文件
		例如：git help commit
		
	
###编辑模式：常用步骤
	1：vi [文件路径] ：打开文件	
	2：按insert 键进入编辑模式  
	3：修改完成以后按ESC键退出编辑模式  
	4：输入：wq退出并保存  
	5：cat [文件路径] :查看文件内容
	
###忽略 .gitignore    
		1.touch .gitignore		创建.gitignore文件，.gitignore文件不能手动创建，只能在命名行下创建  
		2.gitignore的配置文件：对于已经在追踪的文件，在配置文件中配置忽略，不会起作用，需要将其目录删除重新配置
		games/**/*.apk			忽略games目录及其子目录下所有apk结尾的文件

###git 检出一个项目中的指定目录或文件 [参考博客链接](https://blog.csdn.net/doujiang_zheng/article/details/78635725 "参考博客链接")
	(1)touch .git/info/sparse-checkout				在.git目录中创建sparse-checkout
	(2)git config core.sparseCheckout true  修改配置使之支持检出，可以用git config --list 查看是否生效
	(3)vi sparse-checkout 编辑sparse-checkout文件，配置要检出的目录或文件;或者用 echo [配置检出的目录] >> .git/info/sparse-checkout 命令将配置目录添加到配置目录下
	(4)git pull [远程仓库] [本地分支]				检出项目

##### 回滚远程仓库

场景：误操作将错误版本提交到了远程仓库，怎么回滚远程仓库到指定版本？

```
现在本地回滚到指定commit id版本
1.git reflog 或git log 查看记录
2.找到要回滚的commit id
3.git reset --hard commit id
4.git push -f origin xxxx
```

