---
layout : post
title : 错误输出
tagline : Supporting tagline
tags : [nginx,php]
category : php
---
{% include JB/setup %}

##如何将php的错误输出到nginx的错误log中去:

通过FastCGI运行的PHP，在用户访问时出现错误，会首先写入到PHP的errorlog中如果PHP的errorlog无法写入，
则会将错误内容返回给FastCGI接口，然后nginx在收到FastCGI的错误返回后记录到了nginx的errorlog中

所以解决nginx下php-fpm不记录php错误日志的办法:
1.修改php-fpm.conf中配置,没有则增加

	catch_workers_output = yes 
	;error_log = log/error_log

2.修改php.ini中配置，没有则增加

	display_errors = off //不显示错误信息(不输出到页面或屏幕上)
	log_errors = On
	;error_log = "/usr/local/lnmp/php/var/log/error_log"
	error_reporting=E_ALL&~E_NOTICE

注：
php-fpm.conf中的php_admin_value[error_log]，php_admin_flag[log_errors]参数会覆盖到php.ini的error_log，log_errors中
如果只想输出到php-fpm的error_log中，则在php-fpm.conf或php.ini中任意配置一个error_log目录，并保证该目录存在。
如果想要输出到nginx的error_log中，则必须去掉这两个参数，然后再nginx中配置error_log参数。
