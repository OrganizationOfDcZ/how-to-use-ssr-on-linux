# how-to-use-ssrClients-on-linux
ssr
今天很累，先开个头吧，刚把ssr在Linux配置好。2018.4.11


2018.4.12（今天开始更新)

1.首先你想要在linux 上使用ssr客户端的话，得下载（我这里安装的是python版本的),所以其他版本的我不会安装，下面只演示python 版本的配置

2.基本工具安装

以下命令均以root用户执行，或sudo方式执行

centos:
yum install git

ubuntu/debian:
apt-get install git

3.获取源代码

进入你想放文件的目录 ，此处以用户文件夹为例
cd
git clone -b manyuser https://github.com/Ssrbackup/shadowsocksr.git

命令执行完毕后会在当前目录(/home/username)新建一个shadowsocksr目录。
（我的是安装在如图的位置）

https://github.com/MRshiwenqiang/how-to-use-ssr-on-linux/blob/master/2018-04-12%2013-38-05%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE.png
