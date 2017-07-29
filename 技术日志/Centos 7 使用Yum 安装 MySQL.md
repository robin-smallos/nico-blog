##Centos7使用Yum安装MySQL

centos从7开始将原先自带的MySQL被更替为mariadb，默认情况下推荐安装mariadb或Percona，如果对于原版有比较深的情节，可以按照如下方式进行安装。

###1、安装YUM Repo

- Repo官方地址：<a href="https://dev.mysql.com/downloads/repo/yum/">点击这里</a>

- 这里选择的是 Red Hat Enterprise Linux 7 / Oracle Linux 7 (Architecture Independent), RPM Package（原因是CentOS就是RedHat重新编译的版本）。下载地址可以点击链接查看，或自己按照规则拼接：
<pre><code>
    wget https://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm
</code></pre>

- 完成后可以检测下md5是否与页面上的一致：
<pre><code>
    md5sum mysql57-community-release-el7-9.noarch.rpm
</code></pre>

- 然后进行repo的安装：
<pre><code>
    rpm -ivh mysql57-community-release-el7-9.noarch.rpm
</code></pre>

###2、安装MySQL

- 使用yum命令即可完成安装
<pre><code>
    yum install mysql-server
</code></pre>

###3、MySQL的启动配置
- 常用命令
<pre><code>
    systemctl start mysqld #启动MySQL
    systemctl stop mysqld #关闭MySQL
    systemctl restart mysqld #重启MySQL
    systemctl status mysqld #查看MySQL运行状态
    systemctl enable mysqld #设置开机启动
    systemctl disable mysqld #关闭开机启动
</code></pre>

###4、配置MySQL
- 获取安装时的临时密码：
<pre><code>
    grep 'temporary password' /var/log/mysqld.log
</code></pre>

- 设置安全选项：
<pre><code>
    mysql_secure_installation
</code></pre>


#####<a href="https://www.biaodianfu.com/centos-7-install-mysql.html">转：标点符的《Centos 7 使用Yum 安装 MySQL》</a>





