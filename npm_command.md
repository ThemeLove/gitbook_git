npm(node package manager) 是node的包管理工具

> 一般npm是随nodejs一起安装的



##### nodejs 相关命令

```bash
node -v				显示nodejs的版本
```

##### npm 常用命令

```
npm -v									显示npm的版本
npm -h									help命令
npm config list							可以查看已经修改的config

#设置key为指定value
npm config set key=value	或	npm config set key value		
eg:设置registry、proxy、https-proxy
npm config set strict-ssl=false		取消ssl验证
npm config set registry=http://registry.npm.taobao.org		设置镜像源
npm config set proxy=http://web-proxy.houston.softwaregrp.net:8080/		设置http代理
npm config set https-proxy=http://web-proxy.houston.softwaregrp.net:8080/	设置https代理

#删除指定key的自定义config
npm config delete key
eg:npm config delete registry	执行之后使用npm默认的镜像源http://registry.npmjs.org

#全局安装，将安装包放在/usr/local或者你node的安装目录下的node_modules目录下
npm install -g 
eg:npm install -g gitbook-cli		全局安装gitbook-cli

#1.将安装包放在 ./node_modules 下（运行 npm 命令时所在的目录），如果没有 node_modules 目录，会在当前#执行 npm 命令的目录下生成 node_modules 目录
#2.如果没有指定安装包,而是项目目录下执行npm install（比如react项目）会根据package.json配置,在当前node_modules目录下安装所需依赖
npm install [packagename]

#启动当前项目，如果是前端项目（比如reat项目）会监听一个本地端口port，可以localhost:prot预览项目；
#一般会在当前项目目录下配合npm install执行
npm start
```



