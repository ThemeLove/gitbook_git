##gitbook的使用 

####一.gitbook的安装 和 卸载
	1.需要先安装nodejs,配置好nodejs的环境变量，之后才能使用npm命令   
	2.npm install -g gitbook-cli  :安装gitbook的命令行工具   
	3.gitbook -V			  :查看gitbook的版本，如果没有安装，会安装gitbook    

####二.gitbook的常用命令  
	  初始化一个项目
	  gitbook init

	  gitbook安装插件，会根据book.json里面的配置安装
	  gitbook install

	  生成静态页面html
	  gitbook build 

	  生成静态网页并且启动本地的一个server：localhost:4000
	  gitbook serve
	
####三.gitbook 其他命令

	  列出所有的gitbook的命令
	  gitbook help
	
	  显示gitbook-cli的帮助信息
	  gitbook --help
	
	  列出本地所有gitbook的版本
	  gitbook ls
	  列出远端可用的gitbook的最新版本
	  gitbook ls-remote
	
	  更新到gitbook最新的版本
	  gitbook update
	
	  卸载对应的gitbook版本
	  gitbook uninstall 2.0.1

	  指定log的级别
	  gitbook build --log=debug
	
	  输出错误信息
	  gitbook build --debug

	  默认输出格式: `website`  同 gitbook build
	  gitbook build --format=website
	
	  更改输出格式: `json`
	  gitbook build --format=json
	
	  更改输出格式: `ebook`
	  gitbook build --format=ebook
