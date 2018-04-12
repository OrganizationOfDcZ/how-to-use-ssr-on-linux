# how-to-use-ssrClients-on-linux
（仅供学习使用）
ssr我在学习Linux时的自我总结吧。
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


![点击此处查看图片](https://github.com/MRshiwenqiang/how-to-use-ssr-on-linux/raw/master/image/1.png)

4.建立配置文件（非常重要的一步)
在shadowsocks目录里有一个config.json文件，将其拷贝到/etc下，如果没有
也可以自己建立一个sudo gedit /etc/shadowsocks.json
然后进行编辑  下面是编辑的内容，按照自己搭建的服务写
{
    "server": "0.0.0.0",
    "server_ipv6": "::",
    "server_port": 8388,
    "local_address": "127.0.0.1",
    "local_port": 1080,

    "password": "m",
    "method": "aes-128-ctr",
    "protocol": "auth_aes128_md5",
    "protocol_param": "",
    "obfs": "tls1.2_ticket_auth_compatible",
    "obfs_param": "",
    "speed_limit_per_con": 0,
    "speed_limit_per_user": 0,

    "additional_ports" : {}, // only works under multi-user mode
    "additional_ports_only" : false, // only works under multi-user mode
    "timeout": 120,
    "udp_timeout": 60,
    "dns_ipv6": false,
    "connect_verbose_info": 0,
    "redirect": "",
    "fast_open": false
}
然后保存退出

5 开启代理

切换到/shadowsocksr/shadowsocks/ 目录
cd shadowsocksr/shadowsocks/


绿色的就是可执行的python文件，如果没看见你的目录就错了，然后运行：

python local.py -c/etc/shadowsocks.json -d start

![点击此处查看图片](https://github.com/MRshiwenqiang/how-to-use-ssr-on-linux/raw/master/image/2.png)


看到这个就是成功了。
