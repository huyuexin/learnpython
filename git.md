我已经要迫不及待安装VIM了但是考虑插件要用到git还是先装一下git：

　　sudo apt-get install git

安装完成之后和github账号关联（若无github账号请直接看下一步）。首先建立全局信息：

　　git config --global user.name "YOUR NAME"

　　git config --global user.email "YOUR EMAIL ADDRESS"

这里将引号中的内容替换成你的github账号信息即可。

默认是全新的系统，没有残留的垃圾文件，于是完全从新建立SSH关联，再根目录下：

　　ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

同样只改引号中的内容，改成和上面相同的邮件地址。这时会问保存位置，直接按回车保存。

然后要求输入passphrase，相当于是设置密码，和github账户密码不同。这个密码是push提交到线上的时候需要输的密码，无特殊保密需求可以直接回车。

然后就生成了一幅字符图。现在需要找密钥：

　　cat .ssh/id_rsa.pub

会产生一长串字符，选中后右键copy。

打开github网页登入账户进入账户settings左边找到SSH，可以清理一下没用的SSH keys，然后新建一个 ，取名任意，粘贴进去cat产生的所有字符。保存即可。

第一次登录push的时候会需要确认SSH key安全，并且输入passphrase。

关于如何修改已经设置的以上信息，请求助github help。

参考： https://help.github.com/articles/set-up-git/
