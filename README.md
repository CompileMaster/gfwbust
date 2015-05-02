经研究发现，ipsec隧道对突破各种网络封锁有奇效。
封锁一般是针对协议和域名进行的，没备案就不能访问，就是这种情况。应用跑在隧道中，无法被外部检测到协议类型和内容，所以暂时可以透过ipsec突破封锁，实现自由访问。

下面是两个脚本的说明：

SeucrityPolicy-Server.cmd ：windows服务端策略生成，默认加入tcp 80（http协议）和tcp 443（https协议） 服务端口，可以同时为加密码客户端和未加密客户端服务。

SecurityPolicy-Client.cmd ：windows客户端策略生成，默认加入tcp 80（http协议）和tcp 443（https协议）访问端口，可以同时访问加密服务端和未加密服务端。

请在被封锁的windows服务端上应用服务端脚本，访问只要应用客户端脚本就能突破封锁实现正常访问。脚本中的psk是共享密钥，服务端和客户端必须一致，建议参与测试的不要改，方便用户访问被封锁网站。


后边会持续改进脚本，以支持数字证书和linux系统，欢迎大家测试，有问题请提交issue。
