一、HiMQTT是首款完整源码的高性能MQTT物联网防火墙 - MQTT Application FireWall，采用epoll模式支持高并发连接。
    [开源版提供完整的防护功能]
	    1. SSL安全加密反向连接
	    2. 数据库SQL注入
	    3. 跨站脚本攻击（XSS)
	    4、DDOS攻击
	    5、密码暴力破解
	    6. TOPIC黑白名单
	    7. 兼容OWASP的ModSecurity的SQL注入/XSS攻击检测等规则
	    8. epoll模型多核数十万的并发连接
	    ..... 
	  
	    (我们最终努力的目标是用人工智能和各种方法防止0DAY漏洞和未知攻击)
	    
二、安装步骤  
  1. 安装OpenSSL和libpcre
  CentOS : 
  	yum install openssl openssl-devel
  	yum install -y pcre pcre-devel 
  	
  Debian/Ubuntu:
  	sudo apt-get install openssl libssl-dev
  	apt-get install libpcre3 libpcre3-dev  
  
  2.编译
  解压到任意目录，make生成himqtt.
  
  3.规则
  规则放在和himqtt同一级的rules目录，注意后缀是.conf或.rule,更多规则请访问
  https://github.com/SpiderLabs/owasp-modsecurity-crs/
  具体请看rules/main.conf详细说明。

  
  4.运行
  默认himqtt前端运行1884（SSL 加密）端口，后端反向代理1883明文端口。
  ./himqtt默认读取当前目录下的confg.cfg文件， 或者./hihimqtt --config /dir/config.cfg
  具体请看config.cfg详细说明， 如果成功打印加载了rules目录下的规则，代表运行成功。
  
  5.MQTT.fx测试
   MQTT.fx配置SSL/TLSL里面打勾，选择TLSv1.2版本，如果选择第一项CA signed server certificate的话，请确认PEM格式的
   证书是CA信任机构签发的。
   具体看doc目录相关图片。
  
三、商业版演示地址
  静态演示，无实际数据，http://101.42.31.94/iotpages/  
  商业版机器学习也可以开源， QQ/微信:4108863 邮件:4108863@qq.com

  
   
  
  
  
  
