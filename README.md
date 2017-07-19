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

zabbix-server2-4全新升级3.0.3版:[zabbix-server2-4全新升级3-0版](http://blog.yancy.cc/2016/06/19/%E6%80%A7%E8%83%BD%E7%9B%91%E6%8E%A7/Zabbix/zabbix-server3-0-3%E7%89%88%E6%9C%AC%E7%8E%AF%E5%A2%83%E5%AE%89%E8%A3%85%E9%83%A8%E7%BD%B2/)

zabbix-server2.4服务端编译安装 [zabbix-server服务端编译安装](http://blog.yancy.cc/2014/10/02/%E6%80%A7%E8%83%BD%E7%9B%91%E6%8E%A7/Zabbix/Zabbix2.4server%E6%9C%8D%E5%8A%A1%E7%AB%AF%E7%BC%96%E8%AF%91%E5%AE%89%E8%A3%85/)

zabbix2.4监控80端口状态 : [zabbix监控80端口状态](http://blog.yancy.cc/2014/10/06/%E6%80%A7%E8%83%BD%E7%9B%91%E6%8E%A7/Zabbix/zabbix%E7%9B%91%E6%8E%A780%E7%AB%AF%E5%8F%A3%E7%8A%B6%E6%80%81/)
zabbix+Grafana安装使用监控结合 ：[zabbix+Grafana安装使用监控结合](http://blog.yancy.cc/2016/06/17/%E6%80%A7%E8%83%BD%E7%9B%91%E6%8E%A7/Zabbix/zabbix-Grafana%E5%AE%89%E8%A3%85%E4%BD%BF%E7%94%A8%E7%BB%93%E5%90%88/)
zabbix监控MySQL-添加自定义监控项 : [zabbix监控MySQL-添加自定义监控项](http://blog.yancy.cc/2014/09/29/%E6%80%A7%E8%83%BD%E7%9B%91%E6%8E%A7/Zabbix/zabbix%E7%9B%91%E6%8E%A7MySQL-%E6%B7%BB%E5%8A%A0%E8%87%AA%E5%AE%9A%E4%B9%89%E7%9B%91%E6%8E%A7%E9%A1%B9/)
zabbix的ICMP_Ping模版实现对客户端网络状态的监控 : [zabbix的ICMP_Ping模版实现对客户端网络状态的监控](http://blog.yangcvo.me/2014/10/01/%E6%80%A7%E8%83%BD%E7%9B%91%E6%8E%A7/Zabbix/zabbix%E7%9A%84ICMP-Ping%E6%A8%A1%E7%89%88%E5%AE%9E%E7%8E%B0%E5%AF%B9%E5%AE%A2%E6%88%B7%E7%AB%AF%E7%BD%91%E7%BB%9C%E7%8A%B6%E6%80%81%E7%9A%84%E7%9B%91%E6%8E%A7/)


zabbix性能监控故障总结 [zabbix性能监控故障总结](http://blog.yangcvo.me/2014/10/04/%E6%80%A7%E8%83%BD%E7%9B%91%E6%8E%A7/Zabbix/zabbix-%E6%95%85%E9%9A%9C%E6%80%BB%E7%BB%93/)



### 时间同步

* 最重要的一点在最后提，请确保你所有的服务器时间都是正确的，为了确保时间ok，请在crontab里面加上定时时间同步。
crontab -l
00 00  * * *    /usr/sbin/ntpdate -u 192.168.1.220




### 监控MySQL模板：

[monitoring mysql with zabbix](github上面下载)


### zabbix监控kvm


```bash

Monitor your KVM resources through Zabbix

安装依赖

python2, libvirt-python (tested with 0.9.12.3, 0.10.2 and 1.1.3.x)

    pip install libvirt-python 

KVM Server 设定程序


cd /usr/local/bin/
wget https://github.com/bushvin/zabbix-kvm-res/raw/master/bin/zabbix-kvm-res.py
chmod a+x zabbix-kvm-res.py
cd /etc/zabbix/zabbix_agentd.d
wget https://github.com/bushvin/zabbix-kvm-res/raw/master/zabbix_agentd.conf/UserParameters
service zabbix-agent restart


Zabbix Server 设定程序


至https://github.com/bushvin/zabbix-kvm-res下载zabbix_kvm.xml
将`zabbix_kvm.xml 汇入至Zabbix Server → Configuration → Templates → Import`
```
