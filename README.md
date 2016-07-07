# zabbix.2.4

从2014年开始接触zabbix，zabbix历经2.0,2.1,2.2数个版本，虽然大多数功能保持不变，但是还是有非常明显的改变。

* 我们来看看zabbix的发展趋势，打开http://index.baidu.com/?tpl=trend&word=zabbix。
``` 
可以看到这个月的日平均指数在950，整体同比增长928%，环比增长10%。nagios月平均指数在308，同比增长13%，环比24%，可以看出zabbix虽然不及nagios的指数高，但是按这个趋势，大有超过nagios之势。
 来观察下zabbix和nagios的岗位需求数，在51job上搜索zabbix相关的岗位，共计有272个，nagios共计668.
以上是2014年3月份写的，现在zabbix百度指数950多，nagios百度指数540多，如我所言，已经超过他了。
虽然接触zabbix时间很长，但是中间相当一段时间没去配置，这次算是重新复习一遍，并把笔记记录在github。
```



#出现乱码：
* 乱码安装包下载地址：https://github.com/yangcvo/

* 参考文档：

```
zabbix2.4版本都已有汉化功能了，直接选择中文就行。

可是低版本的就需要安装汉化，可是发现打开图形界面是空白图形：

遇到中文乱码问题。zabbix乱码是怎么照成的呢？zabbix使用DejaVuSan.ttf字体，不支持中文，导致中文出现乱码。解决方法很简单，把我们电脑里面字体文件传到zabbix服务器上。


在zabbix-server端上面进入安装目录：

var/www/html/zabbix/fonts目录下面查看，发现之前上传字体的文件名后缀是.ttc，猜着一般见到的都后缀都是ttf的，会不会是这个问题导致的呢。于是在windows系统上找到simkai.ttf,上传到fonts下，编辑/var/www/html/zabbix/include/defines.inc.php，更改：


    define(‘ZBX_FONT_NAME‘, ‘simkai‘);

    define(‘ZBX_GRAPH_FONT_NAME‘,  ‘simkai‘);


没有simfang.ttf 文件的可以到我github下载：

    https://github.com/yangcvo/zabbix.2.4.git

设置好了，服务重启下，刷新，图下面就有字体了：
 

常见问题：
依旧乱码：通过以上的操作，大部分同学的乱码问题解决了，但是依旧有一些同学还是乱码？细心的群友提供另外一种情况：初始化数据库的时候未使用utf8编码所致.初始化数据库使用命令

    create database zabbix default charset utf8;
   
或者my.cnf增加如下配置

    default-character-set = utf8

5. 总结 
乱码处理方法很简单，实际上就是替换字体。
```



#时间同步

* 最重要的一点在最后提，请确保你所有的服务器时间都是正确的，为了确保时间ok，请在crontab里面加上定时时间同步。
crontab -l
00 00  * * *    /usr/sbin/ntpdate -u 192.168.1.220


#监控MySQL模板：

* 下载：https://github.com/yangcvo/zabbix.2.4.git

* monitoring mysql with zabbix：http://www.sysopen.cn/20160515/


