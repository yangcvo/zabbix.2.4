# zabbix.2.4


4. 时间同步
最重要的一点在最后提，请确保你所有的服务器时间都是正确的，为了确保时间ok，请在crontab里面加上定时时间同步。

# crontab -l
00 00  * * *    /usr/sbin/ntpdate -u 192.168.1.220


乱码安装包下载地址：https://github.com/yangcvo/zabbix.2.4.git
