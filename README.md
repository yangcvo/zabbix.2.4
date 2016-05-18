# zabbix.2.4

从2014年开始接触zabbix，zabbix历经2.0,2.1,2.2数个版本，虽然大多数功能保持不变，但是还是有非常明显的改变。

* 我们来看看zabbix的发展趋势，打开http://index.baidu.com/?tpl=trend&word=zabbix，可以看到这个月的日平均指数在950，整体同比增长928%，环比增长10%。nagios月平均指数在308，同比增长13%，环比24%，可以看出zabbix虽然不及nagios的指数高，但是按这个趋势，大有超过nagios之势。
* 来观察下zabbix和nagios的岗位需求数，在51job上搜索zabbix相关的岗位，共计有272个，nagios共计668.
以上是2014年3月份写的，现在zabbix百度指数950多，nagios百度指数540多，如我所言，已经超过他了。
* 虽然接触zabbix时间很长，但是中间相当一段时间没去配置，这次算是重新复习一遍，并把笔记记录在github。




####出现乱码：
乱码安装包下载地址：https://github.com/yangcvo/zabbix.2.4.git

参考文档：http://www.sysopen.cn/20150516/



####时间同步
最重要的一点在最后提，请确保你所有的服务器时间都是正确的，为了确保时间ok，请在crontab里面加上定时时间同步。
crontab -l
00 00  * * *    /usr/sbin/ntpdate -u 192.168.1.220


####监控MySQL模板：

下载：https://github.com/yangcvo/zabbix.2.4.git

monitoring mysql with zabbix：http://www.sysopen.cn/20160616-2/


