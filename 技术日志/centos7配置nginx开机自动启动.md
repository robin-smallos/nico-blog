## centos7利用Systemd配置nginx开机自动启动.md

-    环境：centos7、nginx1.9.4
-    需求：镜像中已有nginx并且配置了虚拟服务器，现在配置开机自动启动
-    方案：使用centos7中集成Systemd实现自启服务
-   Systemd介绍
    +   systemd 是 Linux 下的一款系统和服务管理器，兼容 SysV 和 LSB 的启动脚本。systemd 的特性有：支持并行化任务；同时采用 socket 式与 D-Bus 总线式激活服务；按需启动守护进程（daemon）；利用 Linux 的 cgroups 监视进程；支持快照和系统恢复；维护挂载点和自动挂载点；各服务间基于依赖关系进行精密控制。
-   参考文档
    +   <a href="https://wizardforcel.gitbooks.io/nginx-doc/content/index.html">Nginx 中文官方文档</a>
    +   <a href="http://www.ruanyifeng.com/blog/2016/03/systemd-tutorial-commands.html">Systemd入门教程 by阮一峰</a>

-   ###开始配置
####systemd 下的 system 或 usr 创建 nginx.service 文件
<pre><code>
    vim /usr/lib/systemd/system/nginx.service
</code></pre>

####nginx服务配置写入到该文件中
<pre><code>
    #服务描述性配置
    [Unit]
    Description=nginx - high performance web server
    Documentation=http://nginx.org/en/docs/
    After=network.target remote-fs.target nss-lookup.target
    #服务关键配置
    [Service]
    Type=forking
    #pid文件位置
    #必须与nginx配置文件中的pid配置路径一致，否则会服务启动失败
    PIDFile=/var/run/nginx.pid
    #启动前检测 nginx配置文件 是否正确
    ExecStartPre=/usr/sbin/nginx -t -c /usr/local/nginx/conf/nginx.conf
    #启动
    ExecStart=/usr/sbin/nginx -c /usr/local/nginx/conf/nginx.conf
    #重启
    ExecReload=/bin/kill -s HUP $MAINPID
    #关闭
    ExecStop=/bin/kill -s QUIT $MAINPID
    PrivateTmp=true
    [Install]
    WantedBy=multi-user.target
</code></pre>

####启动服务
<pre><code>
    systemctl start nginx.service
</code></pre>

####关闭服务
<pre><code>
    systemctl stop nginx.service
</code></pre>

####关闭服务
<pre><code>
    systemctl reload nginx.service
</code></pre>

####设置开机自启
 <pre><code>
    systemctl enable nginx.service
 </code></pre>

####查看nginx进程
 <pre><code>
    ps -ef | grep nginx
 </code></pre>

