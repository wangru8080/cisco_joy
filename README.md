# cisco joy

Joy是一个捕获数据包、分析网络流量数据、网络研究取证及安全监控的工具。能够解析pcap包，生成json文件，里面包含了多种网络流量特征，方便对其进行分析。

详情参考http://netsecurity.51cto.com/art/201601/504015.htm 以及https://github.com/cisco/joy 

其中cisco论文使用到joy工具并提取流量特征，进而进行相关分析。参考cisco论文：《Deciphering Malware’s use of TLS (without Decryption)》 链接:https://arxiv.org/pdf/1607.01639.pdf

## 在Ubuntu环境下配置Cisco的joy以及遇到的坑

参考：https://github.com/cisco/joy/wiki/Building

## building
1. sudo apt-get install build-essential libssl-dev libpcap-dev libcurl4-openssl-dev
2. git clone https://github.com/cisco/joy.git

   cd joy
3. ./config
4. make

## 遇到的坑
在./config阶段报错，提示缺少libz库，只用sudo apt-get install zlib1g zlib1g-dev即可
