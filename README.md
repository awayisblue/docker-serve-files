## docker-serve-files
提供资源文件集中管理的仓库。使用docker进行部署及访问。

## 怎么添加资源文件
资源文件需要存放在assets文件夹里，assets文件夹里的目录结果可以任意。
比如有文件 asssets/projects/foo/axios.js, 则访问时是DOMAIN/projects/foo/axios.js

## 环境变量配置

### ASSETS_SERVER_NAME
配置域名，默认 localhost
### ASSETS_EXT
配置静态文件后缀，默认 jpg|jpeg|png|gif|ico|mp3|mp4|json|eot|ttf|woff
### ASSETS_EXPIRES
配置静态文件缓存，默认30d
### STYLEJS_EXT
配置样式及代码文件后缀，默认 css|js
### STYLEJS_EXPIRES
配置样式及代码文件缓存，默认7d

## 怎么上传到docker hub
- 需要有docker hub的账号
- 需要在电脑安装docker，并启动
- 打开terminal, 进行docker登录
 - 运行 `docker login`, 输入在docker hub的账号及密码
 - cd到 `docker-serve-files`
 - 运行 `docker build -t awayisblue/docker-serve-files .`, 其中，awayisblue是docker id， 这里需要改成你实际的docker id
 - 运行 `docker push awayisblue/docker-serve-files`, 注意awayisblue需要换成你的docker id
 - 去docker hub里，就可以查看到你的docker镜像了。

