&lt;!--  
 /\* Font Definitions \*/  
 @font-face  
	{font-family:Helvetica;  
	panose-1:2 11 6 4 2 2 2 2 2 4;  
	mso-font-charset:0;  
	mso-generic-font-family:swiss;  
	mso-font-pitch:variable;  
	mso-font-signature:-536858881 -1073711013 9 0 511 0;}  
@font-face  
	{font-family:宋体;  
	panose-1:2 1 6 0 3 1 1 1 1 1;  
	mso-font-alt:SimSun;  
	mso-font-charset:134;  
	mso-generic-font-family:auto;  
	mso-font-pitch:variable;  
	mso-font-signature:3 680460288 22 0 262145 0;}  
@font-face  
	{font-family:"Cambria Math";  
	panose-1:2 4 5 3 5 4 6 3 2 4;  
	mso-font-charset:1;  
	mso-generic-font-family:roman;  
	mso-font-pitch:variable;  
	mso-font-signature:0 0 0 0 0 0;}  
@font-face  
	{font-family:等线;  
	panose-1:2 1 6 0 3 1 1 1 1 1;  
	mso-font-alt:DengXian;  
	mso-font-charset:134;  
	mso-generic-font-family:auto;  
	mso-font-pitch:variable;  
	mso-font-signature:-1610612033 953122042 22 0 262159 0;}  
@font-face  
	{font-family:"\@宋体";  
	panose-1:2 1 6 0 3 1 1 1 1 1;  
	mso-font-charset:134;  
	mso-generic-font-family:auto;  
	mso-font-pitch:variable;  
	mso-font-signature:3 680460288 22 0 262145 0;}  
@font-face  
	{font-family:"\@等线";  
	panose-1:2 1 6 0 3 1 1 1 1 1;  
	mso-font-charset:134;  
	mso-generic-font-family:auto;  
	mso-font-pitch:variable;  
	mso-font-signature:-1610612033 953122042 22 0 262159 0;}  
 /\* Style Definitions \*/  
 p.MsoNormal, li.MsoNormal, div.MsoNormal  
	{mso-style-unhide:no;  
	mso-style-qformat:yes;  
	mso-style-parent:"";  
	margin:0cm;  
	margin-bottom:.0001pt;  
	text-align:justify;  
	text-justify:inter-ideograph;  
	mso-pagination:none;  
	font-size:10.5pt;  
	mso-bidi-font-size:11.0pt;  
	font-family:等线;  
	mso-ascii-font-family:等线;  
	mso-ascii-theme-font:minor-latin;  
	mso-fareast-font-family:等线;  
	mso-fareast-theme-font:minor-fareast;  
	mso-hansi-font-family:等线;  
	mso-hansi-theme-font:minor-latin;  
	mso-bidi-font-family:"Times New Roman";  
	mso-bidi-theme-font:minor-bidi;  
	mso-font-kerning:1.0pt;}  
.MsoChpDefault  
	{mso-style-type:export-only;  
	mso-default-props:yes;  
	font-family:等线;  
	mso-bidi-font-family:"Times New Roman";  
	mso-bidi-theme-font:minor-bidi;}  
 /\* Page Definitions \*/  
 @page  
	{mso-page-border-surround-header:no;  
	mso-page-border-surround-footer:no;}  
@page WordSection1  
	{size:595.3pt 841.9pt;  
	margin:72.0pt 90.0pt 72.0pt 90.0pt;  
	mso-header-margin:42.55pt;  
	mso-footer-margin:49.6pt;  
	mso-paper-source:0;  
	layout-grid:15.6pt;}  
div.WordSection1  
	{page:WordSection1;}  
--&gt;  


**开关机类命令\(线上服务器禁用\)**

**shutdown关机**

语法格式shutdown \[OPTIONS…\] \[TIME\] \[WALL…\]

常用选项：

-r关机后重启

-h将系统关机

-c取消关机

例如：shutdnow -h -now马上关机shutdnow +30：30分钟后关机

**halt关机**

poweroff关闭系统并且切断电源

-n：关闭操作系统时不执行sync操作；

-w：不真正关闭操作系统，仅在日志文件“/var/log/wtmp”中；

-d：关闭操作系统时，不将操作写入日志文件“/var/log/wtmp”中添加相应的记录；

-f：强制关闭操作系统；

-i：关闭操作系统之前关闭所有的网络接口；

-h：关闭操作系统之前将系统中所有的硬件设置为备用模式。

如果确认系统中已经没有用户存在且所有数据都已保存，需要立即关闭系统，可以使用poweroff命令。

**reboot重启命令**用来重新启动正在运行的Linux操作系统



**文本查看类命令**

**cat命令**concatenate查看文本文件内容

语法格式cat \[OPTION\]… \[FILE\]…

常用选项

-n给每行编号，包括空行

-E显示空格符，包括空行

**tac命令**将文件以行为单位反序输出，最后一行先显示

语法格式tac \[OPTION\]… \[FILE\]…

**less命令**翻屏查看文件

less file

按一下回车键往文件尾部查看一行，按空格键往文件尾部翻一屏

按pageup和pagedown键前后翻屏，按上下箭头可以上下翻一行

**more命令**从头到尾查看文件，不可以回头，不是很好用

**head命令**显示文件的前n行，默认是显示前十行

语法格式：head \[参数\]… \[文件\]…

常用选项：-v显示文件名

-c&lt;字节&gt;显示字节数。head -c 50 /etc/rc.d/init.d/functions显示前50字节，要是改为-50.则显示文件后50字节。

-n&lt;行数&gt;显示的行数。显示文件的前50行：head -50 /etc/rc.d/init.d/functions

**tail命令**显示指定文件末尾内容，不指定文件时，作为输入信息进行处理。常用查看日志文件。

语法格式:tail \[选项\]文件

常用选项-n：查看文件尾部n行

-f：查看文件尾部内容结束后不退出，接着显示更新的行。很有用

例如：tail -3f /tmp/functions查看functions文件尾部3行后不退出

**stat命令：**显示文件和文件的系统熟性，包括文件名，大小，时间戳等信息，通俗地说就像我们看到windows右键，文件属性看到的信息类似。

例如

\[root@dxl ~ 10:30:55\]\# stat /tmp/functions

File: \`/tmp/functions’

Size: 25427 Blocks: 56 IO Block: 4096 regular file

Device: 803h/2051d Inode: 391743 Links: 1

Access: \(0644/-rw-r–r–\) Uid: \( 0/ root\) Gid: \( 0/ root\)

Access: 2017-09-17 10:18:47.899001385 +0800

Modify: 1982-09-19 08:08:39.000000000 +0800

Change: 2017-09-16 13:44:53.754984934 +0800

**日期时间类**

**date命令**用来显示或设定系统的日期与时间。只有root用户可用。当系统正有一个以上的用户在运行时，不要更改日期。

语法格式：Pdate \[OTION\]… \[+FORMAT\]

常用格式符：

%F以年-月-日显示。例如

\[root@dxl ~ 11:10:31\]\# date +%F

2017-09-17

%T时间，包含时分秒

%Y年份，四位显示

%m月份，01-12显示

%d日期，01-31显示

%H小时，00-23显示

%M分钟00-59显示

%S秒

%s:从1970年1月1号\(unix元年\)0点0分0秒到命令执行那一刻经过的秒数；

设定日期格式：date \[月日小时分钟年（可用四位也可以两位）\]\[.秒\]例如

\[root@dxl ~ 11:32:25\]\# date 062811282010.10

Mon Jun 28 11:28:10 CST 2010

\[root@dxl ~ 11:28:10\]\# date 0628112811.10

Tue Jun 28 11:28:10 CST 2011

**clock=hwclock硬件时钟命令**显示或设定硬件时钟

-s, –htocsys：以硬件为准，把系统调整为与硬件时间相同；

例如：我的系统时间不对了

\[root@dxl ~ 12:09:29\]\# date

Tue Jun 28 12:09:33 CST 2011

\[root@dxl ~ 12:09:33\]\# hwclock

Sun 17 Sep 2017 12:18:56 PM CST -0.783353 seconds

\[root@dxl ~ 12:09:57\]\# hwclock -s

\[root@dxl ~ 12:19:12\]\# datte

-bash: datte: command not found

\[root@dxl ~ 12:19:14\]\# date

Sun Sep 17 12:19:20 CST 2017

-w, –systohc：以系统为准，把硬件时间调整为与系统时钟相同；

**网络相关类**

**ifconfig或ip addr list**查看活动接口的ip地址

**ss命令**ss是Socket Statistics的缩写。顾名思义，ss命令可以用来获取socket统计信息，它可以显示和netstat类似的内容。但ss的优势在于它能够显示更多更详细的有关TCP和连接状态的信息，而且比netstat更快速更高效。

例如查看22端口状态：ss -tnl

\[root@dxl ~ 12:35:54\]\# ss -tnl

State Recv-Q Send-Q Local Address:Port Peer Address:Port

LISTEN 0 128 :::22 :::\*

LISTEN 0 128 \*:22 \*:\*

LISTEN 0 100 ::1:25 :::\*

LISTEN 0 100 127.0.0.1:25 \*:\*

**ping命令**测试网络的目标主机和当前主机的连通性，例如

\[root@dxl ~ 12:24:59\]\# ping www.baidu.com

PING www.a.shifen.com \(14.215.177.39\) 56\(84\) bytes of data.

64 bytes from 14.215.177.39: icmp\_seq=1 ttl=55 time=7.17 ms

64 bytes from 14.215.177.39: icmp\_seq=2 ttl=55 time=6.11 ms

….

这表示网络可以连通

**用户管理类**

useradd添加用户命令

例如~\]\# useradd -s /bin/tcsh centos7添加一个叫centos7的用户并指定它的shell为tcsh

**搜索和查询类**

**file命令**查看文件内容类型

例如

\[root@dxl /tmp 16:56:00\]\# file /etc/fstab

/etc/fstab: ASCII text

可以知道fstab是一个标准的文本文件

**type命令**判断一个命令是外部命令还是内部命令

语法格式type COMMAND

**help命令**用于shell内部命令的帮助信息

语法格式help COMMAND

**man命令**帮助手册

语法格式man COMMAND

**Info命令**在线获取命令帮助

**which命令**用于查找某个可执行的命令文件的位置

格式which命令名称

例如：

\[root@dxl /tmp 17:13:02\]\# which passwd

/usr/bin/passwd

**whereis命令**只能用于程序名的搜索，而且只搜索二进制文件例如：whereis ls

语法格式whereis \[options\] name…

常用选项：

-b:仅搜索二进制程序路径

-m:仅搜索使用手册文件路径；

**who命令**识别当前登录的用户，显示关于当前在本地系统上的所有用户的信息

**w命令**显示目前登入系统的用户信息

**语法：**w \[-fhlsuV\]\[用户名称\]

常用选项：

-f　开启或关闭显示用户从何处登入系统。

-h　不显示各栏位的标题信息列。

-l　使用详细格式列表，此为预设值。

-s　使用简洁格式列表，不显示用户登入时间，终端机阶段作业和程序所耗费的CPU时间。

-u　忽略执行程序的名称，以及该程序耗费CPU时间的信息。

-V　显示版本信息。

**history命令**命令历史是bash基础特性之一

history命令默认最大的保存条数是1000条，存放在用户家目录下.bash\_history

控制history条数的环境变量:HISTSIZE控制当前shell进程可保留的条数

HISTFILESIZE:控制命令历史文件.bash\_history保存的条数

HISTSIZE=100

HISTFILESIZE=100这两行追加到当前用户家目录下的.bash\_profile文件中就可以改变默认值，要是都设为零，那么久禁用了历史命令记录。

**命令用法：**

history -c清除当前shell进程中的命令记录

history -d offset:删除历史记录的第n条命令，例如:history -d5删除第五条命令记录

history -r:从历史文件列表到当前历史记录列表中

history -w:

**调用命令历史列表的命令**

!!或ctrl+p :重复执行上一次命令

!n :执行历史命令列表第n条命令，例如!5,执行命令列表第5条命令

!STRING:执行命令历史列表中最近一个以STRING开头的命令。还可以输入Ctrl+R进行搜索。

小技巧：调用上一条命令的最后一个参数：

快捷键：ESC, .

字符串：!$

例如：我执行了ls /etc/sysconfig/network-scripts/ifcfg-eth后，然后在其他命令想再调用后面的参数/etc/sysconfig/network-scripts/ifcfg-eth，先按下ESC键再按.就会引用进来。很实用。







