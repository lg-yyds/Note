DD网络重装脚本

PS：自定义密码直接 -p 你想要的密码就行！！！

部分机器需要设置网卡，否则可以VNC，但是不能远程SSH

-firmware                额外的驱动支持

-d                        Debian系统 后面是系统版本号

-c                        Centos系统 后面是系统版本号

-v                         后面写64位 32位

-a                        auto，全自动无人值守安装

--mirror                后面是镜像源地址

-p                        后面写自定义密码

–ip-addr                 ifconfig -a 后获取到的 例：194.87.xxx.xxx

–ip-gate                 route -n    后获取到的 例   194.87.xxx.xxx

–ip-mask                 255.255.xxx.xx


· 甲骨文、三毛、Vir、RN等大部分VPS通用，三毛、甲骨文 记得去掉 -firmware

旧

bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 11 -v 64 -a -firmware -p 自定义密码


新

bash <(wget --no-check-certificate -qO- 'https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh') -d 11 -v 64 -p 密码 -port 端口 -a -firmware


PS:如果你是腾讯云记得卸载组件 否则会导致报错 DD失败

systemctl stop tat_agent

systemctl disable tat_agent

rm -rf /etc/systemd/system/tat_agent.service

rm -fr /usr/local/qcloud

ps -A | grep agent

# 检查看是否还有腾讯云组件

# kill 这个进程

复制代码

· 国内VPS需要更换镜像源否则很慢！我这里使用的华为源，如果你是腾讯云后面可以换成内网源，节省流量，下面有写！

bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 11 -v 64 -a --mirror 'https://mirrors.huaweicloud.com/debian/' -p 自定义密码



镜像站地址

官方给出的地址列表：https://www.debian.org/mirror/list

一些国内的

ftp.cn.debian.org
mirror.bjtu.edu.cn
mirror.lzu.edu.cn        
mirror.nju.edu.cn        
mirrors.163.com        
mirrors.bfsu.edu.cn        
mirrors.hit.edu.cn        
mirrors.huaweicloud.com        
mirror.sjtu.edu.cn        
mirrors.tuna.tsinghua.edu.cn        
mirrors.ustc.edu.cn        

使用方法：（大致都是一样的）

清华源

--mirror 'https://mirrors.ustc.edu.cn/debian/'
腾讯源

--mirror 'http://mirrors.tencent.com/debian/'
--mirror 'http://mirrors.cloud.tencent.com/debian/'

腾讯源内网（dd完毕后可以修改 走内网速度更快）

http://mirrors.tencentyun.com/
阿里源

--mirror 'https://mirrors.aliyun.com/debian/'

华为源

--mirror 'https://mirrors.huaweicloud.com/debian/'


· DD windows

https://git.beta.gs/

安装重装系统的前提组件:

Debian/Ubuntu:

apt-get install -y xz-utils openssl gawk file wget screen && screen -S os

RedHat/CentOS:

yum install -y xz openssl gawk file glibc-common wget screen && screen -S os

如果出现异常，请刷新Mirrors缓存或更换镜像源。

RedHat/CentOS:

yum makecache && yum update -y

Debian/Ubuntu:

apt update -y && apt dist-upgrade -y


使用:

wget --no-check-certificate -O NewReinstall.sh https://git.io/newbetags && chmod a+x NewReinstall.sh && bash NewReinstall.sh


如为CN主机(部分主机商已不能使用)，可能出现报错或不能下载脚本的问题，可执行以下命令开始安装.

wget --no-check-certificate -O NewReinstall.sh https://cdn.jsdelivr.net/gh/fcurrk/reinstall@master/NewReinstall.sh && chmod a+x NewReinstall.sh && bash NewReinstall.sh

41合一系统密码：

1、CentOS 7.7 (已关闭防火墙及SELinux，默认密码Pwd@CentOS)

2、CentOS 7 (默认密码cxthhhhh.com)

3、CentOS 7 (支持ARM64、UEFI，默认密码cxthhhhh.com)

4、CentOS 8 (默认密码cxthhhhh.com)

5、Rocky 8 (默认密码cxthhhhh.com)

6、Rocky 8 (支持UEFI，默认密码cxthhhhh.com)

7、Rocky 8 (支持ARM64、UEFI，默认密码cxthhhhh.com)

8、CentOS 9 (默认密码cxthhhhh.com)

9、CentOS 6 (官方源原版，默认密码Minijer.com)

10、Debian 11 (官方源原版，默认密码Minijer.com)

11、Debian 10 (官方源原版，默认密码Minijer.com)

12、Debian 9 (官方源原版，默认密码Minijer.com)

13、Debian 8 (官方源原版，默认密码Minijer.com)

14、Ubuntu 20.04 (官方源原版，默认密码Minijer.com)

15、Ubuntu 18.04 (官方源原版，默认密码Minijer.com)

16、Ubuntu 16.04 (官方源原版，默认密码Minijer.com)

17、Windows Server 2022 (默认密码cxthhhhh.com)

18、Windows Server 2022 (支持UEFI，默认密码cxthhhhh.com)

19、Windows Server 2019 (默认密码cxthhhhh.com)

20、Windows Server 2016 (默认密码cxthhhhh.com)

21、Windows Server 2012 (默认密码cxthhhhh.com)

22、Windows Server 2008 (默认密码cxthhhhh.com)

23、Windows Server 2003 (默认密码cxthhhhh.com)

24、Windows 10 LTSC (默认密码Teddysun.com)

25、Windows 10 LTSC (支持UEFI，默认密码Teddysun.com)

26、Windows 7 x86 Lite (默认密码nat.ee)

27、Windows 7 x86 Lite (阿里云专用，默认密码nat.ee)

28、Windows 7 x64 Lite (默认密码nat.ee)

29、Windows 7 x64 Lite (支持UEFI，默认密码nat.ee)

30、Windows 10 LTSC Lite (默认密码nat.ee)

31、Windows 10 LTSC Lite (阿里云专用，默认密码nat.ee)

32、Windows 10 LTSC Lite (支持UEFI，默认密码nat.ee)

33、Windows Server 2003 Lite (C盘默认10G，默认密码WinSrv2003x86-Chinese)

34、Windows Server 2008 Lite (默认密码nat.ee)

35、Windows Server 2008 Lite (支持UEFI，默认密码nat.ee)

36、Windows Server 2012 Lite (默认密码nat.ee)

37、Windows Server 2012 Lite (支持UEFI，默认密码nat.ee)

38、Windows Server 2016 Lite (默认密码nat.ee)

39、Windows Server 2016 Lite (支持UEFI，默认密码nat.ee)

40、Windows Server 2022 Lite (默认密码nat.ee)

41、Windows Server 2022 Lite (支持UEFI，默认密码nat.ee)

99、自定义镜像


宝塔面板7.7.0

https://github.com/8838/btpanel-v7.7.0

curl -sSO https://raw.githubusercontent.com/8838/btpanel-v7.7.0/main/install/install_panel.sh && bash install_panel.sh

1，屏蔽手机号

sed -i "s|bind_user == 'True'|bind_user == 'XXXX'|" /www/server/panel/BTPanel/static/js/index.js

2，删除强制绑定手机js文件

rm -f /www/server/panel/data/bind.pl

3，手动解锁宝塔所有付费插件为永不过期

文件路径：/www/server/panel/data/plugin.json

搜索字符串："endtime": -1全部替换为"endtime": 999999999999

4，给plugin.json文件上锁防止自动修复为免费版

chattr +i /www/server/panel/data/plugin.json



常用脚本


一键开启BBR（适用于较新的Debian、Ubuntu）

echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf

echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf

sysctl -p

sysctl net.ipv4.tcp_available_congestion_control

lsmod | grep bbr



superbench
wget -qO- git.io/superbench.sh | bash



Bench.sh

wget -qO- bench.sh | bash



三网测速
bash <(curl -Lso- https://git.io/superspeed_uxh)


bash <(curl -Lso- https://git.io/J1SEh)

wget -O jcnf.sh https://raw.githubusercontent.com/Netflixxp/jcnfbesttrace/main/jcnf.sh

bash jcnf.sh



yabs 机器跑分

curl -sL yabs.sh | bash



一键安装docker

国外

curl -sSL https://get.docker.com/ | sh


国内

curl -sSL https://get.daocloud.io/docker | sh



卸载docker

sudo apt-get remove docker docker-engine

rm -fr /var/lib/docker/



流媒体测试

全媒体测试

bash <(curl -L -s https://raw.githubusercontent.com/lmc999/RegionRestrictionCheck/main/check.sh)


奈飞测试

wget -O nf https://github.com/sjlleo/netflix-verify/releases/download/2.5/nf_2.5_linux_amd64 && chmod +x nf && clear && ./nf

#第一个

bash <(curl -L -s https://raw.githubusercontent.com/lmc999/RegionRestrictionCheck/main/check.sh)

# 第二个

bash <(curl -sSL "https://github.com/CoiaPrant/MediaUnlock_Test/raw/main/check.sh")




Glances：跨平台的系统性能监控利器

curl -L https://bit.ly/glances | bash

wget -O- https://bit.ly/glances | bash
