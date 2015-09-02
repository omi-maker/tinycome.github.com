---
layout : post
title : php-fpm restart
tagline : Supporting tagline
tags : [Linux,php,php-fpm]
category : php
---
{% include JB/setup %}

php-fpm的master进程可以理解以下信号

INT, TERM 立刻终止

QUIT 平滑终止

USR1 重新打开日志文件

USR2 平滑重载所有worker进程并重新载入配置和二进制模块

示例：

php-fpm 关闭：

	kill -INT `cat /usr/local/php/var/run/php-fpm.pid`

php-fpm 重启：

	kill -USR2 `cat /usr/local/php/var/run/php-fpm.pid`   

查看php-fpm进程数：

	ps aux | grep -c php-fpm

	ps aux | grep php-fpm --中的master process的pid跟/usr/local/php/var/run/php-fpm.pid是一致的
