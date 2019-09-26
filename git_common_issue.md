##git 常见问题    
####1.git log 命令中文乱码  
	commit 描述部分如果有中文，显示乱码  

![](/images/git_log_luanma.png)       

	解决办法：
	1.运行git bash窗口，在导航窗口右键选择菜单options->Text,设置： 
	  Locale:zh_CN  
	  Charector set: UTF-8   
![](/images/git_bash_options_text_settings.png)           

	2.回到git bash 命令行窗口输入如下设置命令 
	git config --global i18n.commitencoding utf-8  		该命令表示提交命令的时候使用utf-8编码集提交
	git config --global i18n.logoutputencoding utf-8 	该命令表示日志输出时使用utf-8编码集显示
	export LESSCHARSET=utf-8  							设置LESS字符集为utf-8	

![](/images/git_log_solve_luanma_command.png)     
     

####2.git log 和 git logref 的区别  
	
	git log 可以显示所有提交过的版本信息，不包括已经被删除的 commit 记录和 reset 的操作
	
	git reflog 是显示所有的操作记录，包括提交，回退的操作。一般用来找出操作记录中的版本号，进行回退  

相关文章链接：  

git log 和 git logref的使用案例：[https://blog.csdn.net/chenpuzhen/article/details/92084229](https://blog.csdn.net/chenpuzhen/article/details/92084229 "git log 和 git logref的使用案例")   

git reflog 恢复已删除分支： [https://blog.csdn.net/changerzhuo_319/article/details/81133533](https://blog.csdn.net/changerzhuo_319/article/details/81133533 "git reflog 恢复已删除分支")    

####3.git stash 详解 
	git stash命令的作用就是将目前还不想提交的但是已经修改的内容进行保存至堆栈中，后续可以在某个分支上恢复出堆栈中的内容。   
	这也就是说，stash中的内容不仅仅可以恢复到原先开发的分支，也可以恢复到其他任意指定的分支上。    
	git stash作用的范围包括工作区和暂存区中的内容，也就是说没有提交的内容都会保存至堆栈中。       

	场景：在工作正常进行时，突然需要切换到其他分支上处理一些东西，这时如果直接切换，那么工作区的改动也会随之跟随到另一个分支，   
		 如果是add然后再commit一下，有感觉麻烦或者是并不合适。只是想将当前状态保存下来，那么 git stash 是一个非常合适命令   

相关文章链接：  
git stash详解：[https://blog.csdn.net/stone_yw/article/details/80795669](https://blog.csdn.net/stone_yw/article/details/80795669 "git stash详解")   
   

####4. 合并冲突  
	pull的时候会提示Please enter a commit message to explain why this merge is necesary.......  
	这是因为本地仓库的修改和远程仓库有冲突，需要解决完冲突之后才提交
	解决办法：
	(1).按键盘字母 i 进入insert模式
	(2).修改最上面那行黄色合并信息,可以不修改
	(3).按键盘左上角"Esc"
	(4).输入":wq",注意是冒号+wq,按回车键即可
