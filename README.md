# zabbix.2.4

从2014年开始接触zabbix，zabbix历经2.0,2.1,2.2数个版本，虽然大多数功能保持不变，但是还是有非常明显的改变。

* 我们来看看zabbix的发展趋势，打开http://index.baidu.com/?tpl=trend&word=zabbix。
``` 
可以看到这个月的日平均指数在950，整体同比增长928%，环比增长10%。nagios月平均指数在308，同比增长13%，环比24%，可以看出zabbix虽然不及nagios的指数高，但是按这个趋势，大有超过nagios之势。
 来观察下zabbix和nagios的岗位需求数，在51job上搜索zabbix相关的岗位，共计有272个，nagios共计668.
以上是2014年3月份写的，现在zabbix百度指数950多，nagios百度指数540多，如我所言，已经超过他了。
虽然接触zabbix时间很长，但是中间相当一段时间没去配置，这次算是重新复习一遍，并把笔记记录在github。
```

下载源码包地址：http://jaist.dl.sourceforge.net/project/zabbix/ZABBIX%20Latest%20Stable/

zabbix-server2-4全新升级3.0.3版:[zabbix-server2-4全新升级3-0版](http://blog.yangcvo.me/2016/07/21/zabbix-server2-4全新升级3-0版本/)

zabbix-server2.4服务端编译安装 [zabbix-server服务端编译安装](http://blog.yangcvo.me/2015/01/18/zabbix-server服务端编译安装/)

zabbix2.4监控80端口状态 : [zabbix监控80端口状态](http://blog.yangcvo.me/2016/07/20/zabbix监控80端口状态/)

zabbix+Grafana安装使用监控结合 ：[zabbix+Grafana安装使用监控结合](http://blog.yangcvo.me/2016/07/13/zabbix-Grafana安装使用结合/)

zabbix监控MySQL-添加自定义监控项 : [zabbix监控MySQL-添加自定义监控项](http://blog.yangcvo.me/2015/09/29/zabbix监控MySQL-添加自定义监控项/)

zabbix的ICMP_Ping模版实现对客户端网络状态的监控 : [zabbix的ICMP_Ping模版实现对客户端网络状态的监控](http://blog.yangcvo.me/2015/11/18/zabbix的ICMP-Ping模版>实现对客户端网络状态的监控/)


zabbix性能监控故障总结 [zabbix性能监控故障总结](http://blog.yangcvo.me/2016/02/07/zabbix-故障总结/)



#时间同步

* 最重要的一点在最后提，请确保你所有的服务器时间都是正确的，为了确保时间ok，请在crontab里面加上定时时间同步。
crontab -l
00 00  * * *    /usr/sbin/ntpdate -u 192.168.1.220




#监控MySQL模板：

* 下载：https://github.com/yangcvo/zabbix.2.4.git

* monitoring mysql with zabbix：http://www.sysopen.cn/20160515/


