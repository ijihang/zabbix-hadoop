Zabbix上的hbase监控模板。
说明
	支持监控hbase监控。
	在CentOS7，Zabbix5.0，Hadoop2.7.6下测试成功。
使用方法
在zabbix前端导入Template Cluster hbase ResourceManager.xml模板文件，链接该模板到hbase主机上，并根据实际情况在继承以及主机宏这里修改三个宏参数：
然后上传剩余的两个脚本文件到Zabbix Server主机上存放Zabbix外部脚本的文件夹（默认为/usr/local/share/zabbix/externalscripts/）中，
并使用chmod +x赋予脚本文件可执行权限。
完成！
当前支持的监控项目(6项)
	locked线程数		
	GC总时间		
	GC总次数		
	HMaster启动时间	
	HMaster是否处于Active状态	
	使用的堆内存大小		
	使用的非堆内存大小		
	发送的数据量（仅适用于Active Master）		
	处于Dead状态的RegionServer节点数（仅适用于Active Master）	
	处于Live状态的RegionServer节点数（仅适用于Active Master）	
	接收到的数据量（仅适用于Active Master）		
	提交的堆内存大小		
	提交的非堆内存大小		
	最大堆内存大小		
	正在执行的线程数		
	等待线程数		
	该主机HMaster变为Active状态时的时间（仅适用于Active Master）
当前支持的触发器项目
	主机{HOSTNAME}上的HBase Master刚刚被重启过		
	在过去的5分钟内未获取到主机[{HOSTNAME}]上HMaster的任何数据，请检查数据采集器的日志或者查看该主机HMaster运行状态		
	处于Live状态的RegionServer节点数量发生了变化		
	当前处于Active状态的HMaster主机为: {HOSTNAME}		
	有一个或者多个RegionServer节点变为Live状态或者重启了		
	有一个或者多个RegionServer节点处于Dead状态
