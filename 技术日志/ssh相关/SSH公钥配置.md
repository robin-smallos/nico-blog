1. ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
2. 输入自定义名称
3. 可以设置rsa访问密码
4. 多个账户需要增加.shh/config文件
    Host git.coding.net
    User xxxx@email.com
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/coding_rsa  // 生成的非默认地址的公钥存放点

就可以设置多个ssh免密访问了