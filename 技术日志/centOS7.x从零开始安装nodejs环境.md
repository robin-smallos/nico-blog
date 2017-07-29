centOS7.x从零开始安装nodejs环境

1.yum安装nodejs
    curl --silent --location https://rpm.nodesource.com/setup_7.x | bash -
    yum install -y nodejs




2.yum安装nginx

-   yum install -y nginx
-   Nginx默认目录

输入命令：
    whereis nginx

即可看到类似于如下的内容：
    nginx: /usr/sbin/nginx /usr/lib64/nginx /etc/nginx /usr/share/nginx

以下是Nginx的默认路径：
    (1) Nginx配置路径：/etc/nginx/
    (2) PID目录：/var/run/nginx.pid
    (3) 错误日志：/var/log/nginx/error.log
    (4) 访问日志：/var/log/nginx/access.log
    (5) 默认站点目录：/usr/share/nginx/html

事实上，只需知道Nginx配置路径，其他路径均可在/etc/nginx/nginx.conf 以及/etc/nginx/conf.d/default.conf 中查询到。

常用命令

-   启动：
    nginx

-   测试Nginx配置是否正确：
    nginx -t

-   优雅重启：
    nginx -s reload

该命令与以下命令类似：
    kill -HUP nginx进程号


3.安装git管理代码
yum install git
yum --version

4.安装nvm管理node版本
curl https://raw.githubusercontent.com/creationix/nvm/v0.30.2/install.sh | bash
nvm --version

常用命令
    nvm install stable
    nvm 查看所有命令

