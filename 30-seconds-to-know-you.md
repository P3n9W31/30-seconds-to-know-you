# 情报收集


## 外围信息收集

### 通过DNS和IP地址挖掘目标的网络信息

#### 已知：域名

- 

	- whois域名注册成信息查询

		- 域名持有者

		- 管理员email、电话、传真

		- 域名服务器信息

		- 注册时间

	- nslookup域名查询

		- 域名IP地址的非权威解答

	- netcraft网站提供的信息查询服务

		- http://searchdns.netcraft.com

			- 子站点

			- 地理位置

			- 服务器地址

			- 服务器操作系统类型

			- 服务器运行状态

			- 站点排名

			- web服务器版本

#### 已知：域名、域名服务器

- dig域名查询

	- 域名IP地址的权威解答

#### 已知：IP地址

- IP2Location地理位置查询

	- GeoIP: [http://www.maxmind.com](http://www)里使用该服务_国外较适用

		- 具体位置

		- 经纬度

- QQ纯真数据库

	- [http://www.cz88.net](http://www.cz88.net) 里使用该服务_国内较适用

		- 具体位置

- IP2Domin反查域名

	- http://www.ip-adress.com/reverse_ip

		- 指向ip的所有域名

		- 地理位置

- 国内IP反查询

	- http://www.7c.com/ 

		- 指向ip的所有域名

### 通过搜索引擎进行信息查询

#### 已知：域名

- Google Hacking技术

	- Windows软件:SiteDigger、Search Diggity

		- 各种信息

- 搜索网站的目录结构

	- Google中指定Site，搜索文件名

		- 网站文件列表的目录

			- 留意robots.txt的反爬虫文件

	- Metasploit的dir_scanner辅助模块

		- 网站隐藏目录

- 检索特定类型的文件

	- Google中指定Site，搜索文件类型

		- 通讯录

		- 账单

		- 用户信息合集

- 搜索网站中的email地址

	- Metasploit的search_email_collector模块

		- 指定网站中包含目标域名的email地址

- 搜索易存在SQL注入点的页面

	- Google1中指定Site，搜索inurl:login

		- 网站的登录界面

## 主机检测与端口扫描

### 活跃主机扫描

#### 已知：域名或IP

- ICMP Ping命令

	- 判断某个主机是否活跃

- Metasploit的主机发现模块

	- arp_sweep(常用)

	- ipv6_multicast_ping

	- ipv6_neighbor

	- ipv6_neighbor_router_advertisement

		- 网段上的所有活跃主机

	- udp_probe

	- upd_sweep(常用)

- 使用Nmap进行主机探测

	- nmap <扫描选项> <扫描目标>

		- 网段上的所有主机

### 操作系统识别

#### 已知：IP

- 使用Nmap探测目标主机的操作系统版本

	- nmap -o 目标地址

		- 主机的操作系统版本

### 端口扫描与服务类型

#### 已知：IP

- Metasploit中的端口扫描器portscan

	- 开放端口

- Nmap端口扫描

	- 端口上开放的服务

	- 服务版本信息

- AutoScan查看网络情况(可能不够精确)

	- 活跃主机

	- 操作系统版本

	- 开放端口和服务

## 服务扫描与查点

### Metasploit中search name:_version显示的模块

#### 已知：IP

- Telnet服务扫描

	- telnet_version

		- 检查有无Telnet服务

- SSH服务扫描

	- ssh_version

		- 检查有无SSH服务

- Oracle服务查点

	- tnslsnr_version

		- 查找开放的Oracle监听服务器

		- Orecle版本号

- 开放代理探测与利用

	- open_proxy

		- 配置代理服务器隐藏IP地址

