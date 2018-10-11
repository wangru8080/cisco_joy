# cisco joy

Joy是一个捕获数据包、分析网络流量数据、网络研究取证及安全监控的工具。能够解析pcap包，生成json文件，里面包含了多种网络流量特征，方便对其进行分析。(目前版本为2.0）

详情参考http://netsecurity.51cto.com/art/201601/504015.htm 以及https://github.com/cisco/joy 

其中cisco论文使用到joy工具并提取流量特征，进而进行相关分析。

参考cisco论文：

《Deciphering Malware’s use of TLS (without Decryption)》 链接:https://arxiv.org/pdf/1607.01639.pdf

《Identifying Encrypted Malware Traffic with Contextual Flow Data》 链接：http://oelvsay9f.bkt.clouddn.com/p35-anderson.pdf

## 1. 在Ubuntu环境下配置Cisco的joy

参考：https://github.com/cisco/joy/wiki/Building

### building
1. sudo apt-get install build-essential libssl-dev libpcap-dev libcurl4-openssl-dev
2. git clone https://github.com/cisco/joy.git

   cd joy
3. ./config
4. make

### 遇到的坑
在./config阶段报错，提示缺少libz库，只用运行命令sudo apt-get install zlib1g zlib1g-dev即可

## 2. 简单使用joy的方法
进入joy/bin目录（假设存在xx.pcap文件）：

运行命令：./joy output=xx.gz xx.pcap

其中生成的xx.gz压缩文件中包含了提取的流量特征的json文件

关于其他使用方法见joy使用手册：https://github.com/cisco/joy/blob/master/doc/using-joy-05.pdf

### 已经将joy编译好了，需要使用的下载bin文件，可以直接使用，不需要其他配置
