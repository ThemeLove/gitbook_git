##git tag （标签）
###git 标签分2种，轻量级标签（lightweight）和附注标签（annotated）

	1.轻量级标签（lightweight):实际上就是一个保存着对应提交对象的校验和信息的应用，指向某次提交。
	2.附注标签（annotated):实际上是存储在仓库中的一个独立对象，它有自身的校验和信息，包含着标签的名字，电子邮件和日期以及标签说明	

		git tag [tag-name]  -m "xxx"   								创建轻量级标签
		git tag -a [tag-name] -m "xxx"								创建附注标签
		git tag -a [tag-name] [某次提交的hash值]						为之前的某次提交加注标签 
		git tag -d [tag-name] 										删除标签  

###分享标签：默认情况下，git push origin master 这种git push 命令并不会把标签传递到远程服务器上，只有通过显示命令才能分享标签

		git push [远程仓库] [tag-name]   							推送指定标签名的tag到远程仓库  
		例如：git push origin v1.1									推送v1.1的tag到远程origin仓库

		git push [远程仓库] --tags									一次推送本地所有标签到远程仓库  
		例如：git push origin --tags									一次推送本地所有标签到远程origin仓库  
###tag其他命令
		git tag						显示已有的标签
		git tag -l "regex"			匹配特定规则的tag
		git show [tag-name]			查看指定标签名的标签详细信息
