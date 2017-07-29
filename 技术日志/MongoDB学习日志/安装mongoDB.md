Install MongoDB Community Edition with Homebrew

1.brew update

2.brew install mongodb

3.在根目录 / 下创建 data/db 目录，用于放置mongodb数据，并且给该目录设置权限
sudo mkdir -p /data/db
sudo chown -R <用户名> /data

4.启动
mongod

5.新建终端输入：mongo