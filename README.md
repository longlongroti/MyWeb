# MyWeb
My web

如何配置多个ssh-key
ssh-keygen -t rsa -C "1522520179@qq.com" -f 'myweb'
$ ssh-add -l
Could not open a connection to your authentication agent.
如果发现上面的提示,说明系统代理里没有任何key,执行如下操作
exec ssh-agent bash

如果系统已经有ssh-key 代理 ,执行下面的命令可以删除

$ ssh-add -D

把 .ssh 目录下的3个私钥添加的 ssh-agent

$ ssh-add ~/.ssh/id_rsa_aaa
$ ssh-add ~/.ssh/id_rsa_bbb

#aaa  (github 配置)
Host aaa
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_rsa_aaa

#bbb  (开源中国 配置)
Host bbb
    HostName git.oschina.net
    User git
    IdentityFile ~/.ssh/id_rsa_bbb