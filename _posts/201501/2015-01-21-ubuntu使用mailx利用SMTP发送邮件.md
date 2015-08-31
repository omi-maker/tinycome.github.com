---
layout : post
title : ubuntu使用mailx利用SMTP发送邮件
tagline : Supporting tagline
tags : [Linux,ubuntu]
category : Linux
---
{% include JB/setup %}

转载：http://www.blogjava.net/jasmine214--love/archive/2010/10/09/334102.html

1、下载安装mailx

	sudo apt-get  install heirloom-mailx

2、修改/etc/nail.rc (/etc/mail.rc)

	set from=username@domain.com smtp=smtp.domain.com
	set smtp-auth-user=username smtp-auth-password=password
	set smtp-auth=login
	eg:
	set from=tiny@163.com smtp=smtp.163n.com
	set smtp-auth-user=tiny smtp-auth-password=123456
	set smtp-auth=login

说明：

from是发送的邮件地址

smtp是发生的外部smtp服务器的地址

smtp-auth-user是外部smtp服务器认证的用户名

smtp-auth-password是外部smtp服务器认证的用户密码

smtp-auth是邮件认证的方式

配置成功后，就可以使用了

可以发送一封邮件测试一下：
	
	mail -s "test" user@sohu.com < content.txt 

其中-s后面的是邮件标题，user@sohu.com是收件人地址，content.txt里面是邮件正文
