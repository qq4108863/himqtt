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
	  HiMQTT是免费的，完全可以用于商业物联网防御，也可以定制开发包括：
	    1. Web管理界面
	    2. OEM 成硬件部署，保护多台物联网服务器 
	    3. 云端虚拟化部署，保护多台物联网服务器
	    4. 物联网网关安全防护
	    5. 更高级有效的防御规则
	    ......
	    (我们最终努力的目标是用人工智能的方法，防止物联网未知漏洞和未知攻击，打造智能物联网安全平台)
	    
二、安装步骤  
  1. 安装OpenSSL和libpcre开发库
  CentOS : 
  	yum install openssl openssl-devel
  	yum install -y pcre pcre-devel 
  	
  Debian/Ubuntu:
  	sudo apt-get install openssl libssl-dev
  	apt-get install libpcre3 libpcre3-dev  
  
  2.编译
  解压到任意目录，make即可，完成后生成可执行文件himqtt.
  
  3.规则
  规则放在和himqtt同一级的rules目录即可，注意后缀是.conf或者.rule,更多规则请在
  https://github.com/SpiderLabs/owasp-modsecurity-crs/下载，根据需求配置。
  具体请看rules/main.conf详细说明。

  
  4.运行
  通常是himqtt前端运行1884（SSL 加密）端口，后端反向代理1883端口。
  首先保证Web服务器1883端口运行正常，1884端口没占用（或者端口在config.cfg里改变配置)
  ./himqtt默认读取当前目录下的confg.cfg文件， 或者./hihimqtt --config /dir/config.cfg
  具体请看config.cfg详细说明， 如果成功打印加载了rules目录下的规则，代表运行成功。
  
  5.MQTT.fx测试
   MQTT.fx配置SSL/TLSL里面打勾，选择TLSv1.2版本，如果选择第一项CA signed server certificate的话，请确认你的PEM格式的
   证书是CA签发的。
   具体看doc目录相关图片。
  
  
  6.需要更多高级防护和web管理功能，请加QQ/微信:4108863  邮件:4108863@qq.com
  
   http://www.hihttps.com/
  
  
  
  
