## **文件和目录操作类**

> **ls命令**  list 列出指定目录下的内容
>
> 语法格式： ls \[OPTION\]… \[FILE\]…
>
> 常用选项：
>
> -a显示所有文件和隐藏文件。
>
> -A显示除.和..之外的所有文件。
>
> -l 长格式列表，显示文件的详细属性信息
>
> -h  –human-readanle,把文件大小单位换算，换算后可能会是非精确值
>
> -d  查看目录自身而非其内部文件列表
>
> -r  reverse，逆序显示
>
> -R  recursive  ,递归显示
>
> -t   显示最后一次修改的文件
>
> -n  打印文件的UID和GID
>
> -i  显示文件的inode信息
>
> -t  用文件和目录的更改时间排序  
> -F  在不同类型的文件的文件名结尾追加一个字符以示区别。可执行文件后加”\*”，目录后加”/”，管道文件后加”\|”，套接字文件后加”=”，普通文件没有后缀。比较有用。
>
> –full-time  列出文件的完整时间格式
>
> 例如：显示/etc里面所有的内容包含隐藏文件  ls  -ali 最左边一列是文件的inode信息。
>
> [![](http://www.178linux.com/wp-content/uploads/2017/09/F2.png "F2")](http://www.178linux.com/wp-content/uploads/2017/09/F2.png)
>
> 出文件的完整时间格式 ls -ali –full-time
>
> [![](http://www.178linux.com/wp-content/uploads/2017/09/F2.png "F2")](http://www.178linux.com/wp-content/uploads/2017/09/F2.png)
>
> 假如我在/tmp下面新建了一个hello.txt文件，可以用ls -lrt 进行逆序按时间排序出最下面找到它：
>
> [![](http://www.178linux.com/wp-content/uploads/2017/09/F3.png "F3")](http://www.178linux.com/wp-content/uploads/2017/09/F3.png)
>
> **pwd命令**   printing working directory 显示当前工作目录
>
> **cd 命令**  change directory 切换目录
>
> cd  不带任何参数表示切换到家目录
>
> cd  ~  切回自己家目录，波浪线~表示家目录
>
> cd  ~  USERNAME 切换到指定用户家目录
>
> cd  –   上一次所在目录和当前目录之间来回切换
>
> .       表示当前目录
>
> cd  ..   切换到当前目录的上一级目录
>
> **touch命令**   用于创建一个新文件或修改文件时间戳
>
> touch \[OPTION\]… FILE…
>
> 常用选项：
>
> -c   –no-create,指定的文件路径不存在时不予创建
>
> -a   仅修改访问时间access time
>
> -m  仅修改modify time（文件内容修改）
>
> -t   使用指定的日期时间，而非现在的时间
>
> **cp命令** copy 用于复制源文件或者目录到
>
> 语法格式：单源复制：cp \[OPTION\]… \[-T\] SOURCE DEST
>
> 多源复制：cp \[OPTION\]… SOURCE… DIRECTORY
>
> 常用选项：
>
> -i：交互式复制，即覆盖之前提醒用户确认；
>
> -f：强制覆盖目标文件；
>
> -r, -R：递归复制目录；
>
> -d：复制符号链接文件本身，而非其指向的源文件；
>
> -a：-dR –preserve=all, archive，用于实现归档；
>
> -p   –preserv=
>
> mode：权限
>
> ownership：属主和属组
>
> timestamps: 时间戳
>
> context：安全标签
>
> xattr：扩展属性
>
> links：符号链接
>
> all：上述所有属性
>
> 保持指定的属性\(默认：模式,所有权,时间戳\)
>
> -P   –no-dereference   不跟随源文件中的符号链接
>
> 实例：单文件复制 复制/etc/fstab到tmp下 文件不存在时：
>
> \[root@dxl /tmp 14:35:16\]\# cp /etc/fstab .
>
> \[root@dxl /tmp 14:36:44\]\# ls
>
> 1.txt  22  33  fstab  functions  hello.txt  test.txt
>
> 复制目录时目标文件夹存在，则把源目录里面的内容复制到目标文件夹里面。要是目标不存在则创建。
>
> **mkdir命令 ** 创建目录make directories
>
> 语法格式： mkdir \[OPTION\]… DIRECTORY…
>
> 常用选项：
>
> -p  通俗地说对于不存在的父和子目录一起创建出来
>
> -v 显示过程
>
> -m 直接给定权限
>
> 注意：路径基名方为命令的作用对象；基名之前的路径必须得存在；
>
> 例如：在tmp下面创建目录centos/a/b/c
>
> \[root@dxl /tmp 15:16:35\]\# mkdir -pv /tmp/centos/a/b/c
>
> mkdir: created directory \`/tmp/centos’
>
> mkdir: created directory \`/tmp/centos/a’
>
> mkdir: created directory \`/tmp/centos/a/b’
>
> mkdir: created directory \`/tmp/centos/a/b/c’
>
> **mv 移动命令**，还可以对文件进行重命名
>
> 语法格式：mv \[OPTION\]… \[-T\] SOURCE DEST
>
> mv \[OPTION\]… SOURCE… DIRECTORY
>
> mv \[OPTION\]… -t DIRECTORY SOURCE…
>
> 常用选项：-f强制移动
>
> -i 交互式
>
> 例如：把tmp下面的1.txt移动到tom文件夹里面并命名为2.txt。
>
> \[root@dxl /tmp 15:23:17\]\# mv 1.txt  ./tom/2.txt
>
> **rm    删除命令**remove
>
> 语法格式： rm \[OPTION\]… FILE…
>
> 常用选项：-f 强制删除
>
> -i  交互
>
> -r  将参数中列出的全部目录和子目录均递归地删除
>
> 注意：删除命令是一个非常危险的操作，所有不用的文件建议不要直接删除，而是移动至某个专用目录；（模拟回收站），过段时间后，非常明确肯定不要了再删除。
>
> ## **开关机类命令\(线上服务器禁用\)**
>
> shutdown 关机命令
>
> 语法格式 shutdown \[OPTIONS…\] \[TIME\] \[WALL…\]
>
> 常用选项：
>
> -r  关机后重启
>
> -h 将系统关机
>
> -c  取消关机
>
> 例如：shutdnow -h -now马上关机  shutdnow  +30 ：30分钟后关机
>
> **halt   关机**
>
> poweroff  关闭系统并且切断电源
>
> -n：关闭操作系统时不执行sync操作；
>
> -w：不真正关闭操作系统，仅在日志文件“/var/log/wtmp”中；
>
> -d：关闭操作系统时，不将操作写入日志文件“/var/log/wtmp”中添加相应的记录；
>
> -f：强制关闭操作系统；
>
> -i：关闭操作系统之前关闭所有的网络接口；
>
> -h：关闭操作系统之前将系统中所有的硬件设置为备用模式。
>
> 如果确认系统中已经没有用户存在且所有数据都已保存，需要立即关闭系统，可以使用poweroff命令。
>
> **reboot 重启命令**  用来重新启动正在运行的Linux操作系统

## 

> ## **文本查看类命令**
>
> **cat命令**  concatenate查看文本文件内容
>
> 语法格式cat \[OPTION\]… \[FILE\]…
>
> 常用选项
>
> -n 给每行编号，包括空行
>
> -E 显示空格符，包括空行
>
> **tac命令** 将文件以行为单位反序输出，最后一行先显示
>
> 语法格式 tac \[OPTION\]… \[FILE\]…
>
> **less命令**   翻屏查看文件
>
> less file
>
> 按一下回车键往文件尾部查看一行，按空格键往文件尾部翻一屏
>
> 按pageup和pagedown键前后翻屏，按上下箭头可以上下翻一行
>
> **more命令  **从头到尾查看文件，不可以回头，不是很好用
>
> **head命令   **显示文件的前n行，默认是显示前十行
>
> 语法格式：head \[参数\]… \[文件\]…
>
> 常用选项：-v 显示文件名
>
> -c&lt;字节&gt; 显示字节数。  head  -c 50 /etc/rc.d/init.d/functions 显示前50字节，要是改为-50.则显示文件后50字节。
>
> -n&lt;行数&gt; 显示的行数。显示文件的前50行：head  -50 /etc/rc.d/init.d/functions
>
> **tail命令**  显示指定文件末尾内容，不指定文件时，作为输入信息进行处理。常用查看日志文件。
>
> 语法格式:tail \[选项\]  文件
>
> 常用选项 -n  ：查看文件尾部n行
>
> -f：查看文件尾部内容结束后不退出，接着显示更新的行。很有用
>
> 例如： tail -3f  /tmp/functions  查看functions文件尾部3行后不退出
>
> ** stat命令：**显示文件和文件的系统熟性，包括文件名，大小，时间戳等信息，通俗地说就像我们看到windows右键，文件属性看到的信息类似。
>
> 例如
>
> \[root@dxl ~ 10:30:55\]\# stat /tmp/functions
>
> File: \`/tmp/functions’
>
> Size: 25427           Blocks: 56         IO Block: 4096   regular file
>
> Device: 803h/2051d      Inode: 391743      Links: 1
>
> Access: \(0644/-rw-r–r–\)  Uid: \(    0/    root\)   Gid: \(    0/    root\)
>
> Access: 2017-09-17 10:18:47.899001385 +0800
>
> Modify: 1982-09-19 08:08:39.000000000 +0800
>
> Change: 2017-09-16 13:44:53.754984934 +0800
>
> ## **日期时间类**
>
> **date命令**  用来显示或设定系统的日期与时间。只有root用户可用。当系统正有一个以上的用户在运行时，不要更改日期。
>
> 语法格式：Pdate \[OTION\]… \[+FORMAT\]
>
> 常用格式符：
>
> %F 以年-月-日显示 。例如
>
> \[root@dxl ~ 11:10:31\]\# date +%F
>
> 2017-09-17
>
> %T  时间，包含时分秒
>
> %Y  年份，四位显示
>
> %m  月份，01-12显示
>
> %d   日期，01-31显示
>
> %H  小时，00-23显示
>
> %M  分钟00-59显示
>
> %S  秒
>
> %s: 从1970年1月1号\(unix元年\)0点0分0秒到命令执行那一刻经过的秒数；
>
> 设定日期格式：date \[月日小时分钟年（可用四位也可以两位）\]\[.秒\]例如
>
> \[root@dxl ~ 11:32:25\]\# date 062811282010.10
>
> Mon Jun 28 11:28:10 CST 2010
>
> \[root@dxl ~ 11:28:10\]\# date 0628112811.10
>
> Tue Jun 28 11:28:10 CST 2011
>
> **clock=hwclock   硬件时钟命令**  显示或设定硬件时钟
>
> -s, –htocsys：以硬件为准，把系统调整为与硬件时间相同；
>
> 例如：我的系统时间不对了
>
> \[root@dxl ~ 12:09:29\]\# date
>
> Tue Jun 28 12:09:33 CST 2011
>
> \[root@dxl ~ 12:09:33\]\# hwclock
>
> Sun 17 Sep 2017 12:18:56 PM CST  -0.783353 seconds
>
> \[root@dxl ~ 12:09:57\]\# hwclock -s
>
> \[root@dxl ~ 12:19:12\]\# datte
>
> -bash: datte: command not found
>
> \[root@dxl ~ 12:19:14\]\# date
>
> Sun Sep 17 12:19:20 CST 2017
>
> -w, –systohc：以系统为准，把硬件时间调整为与系统时钟相同；
>
> ## **网络相关类**
>
> **ifconfig  或ip addr list**  查看活动接口的ip地址
>
> **ss命令**  ss是Socket Statistics的缩写。顾名思义，ss命令可以用来获取socket统计信息，它可以显示和netstat类似的内容。但ss的优势在于它能够显示更多更详细的有关TCP和连接状态的信息，而且比netstat更快速更高效。
>
> 例如查看22端口状态 ：ss  -tnl
>
> \[root@dxl ~ 12:35:54\]\# ss -tnl
>
> State      Recv-Q Send-Q        Local Address:Port          Peer Address:Port
>
> LISTEN     0      128                      :::22                      :::\*
>
> LISTEN     0      128                       \*:22                       \*:\*
>
> LISTEN     0      100                     ::1:25                      :::\*
>
> LISTEN     0      100               127.0.0.1:25                       \*:\*
>
> **ping命令**  测试网络的目标主机和当前主机的连通性  ，例如
>
> \[root@dxl ~ 12:24:59\]\# ping www.baidu.com
>
> PING www.a.shifen.com \(14.215.177.39\) 56\(84\) bytes of data.
>
> 64 bytes from 14.215.177.39: icmp\_seq=1 ttl=55 time=7.17 ms
>
> 64 bytes from 14.215.177.39: icmp\_seq=2 ttl=55 time=6.11 ms
>
> ….
>
> 这表示网络可以连通
>
> ## **用户管理类**
>
> useradd  添加用户命令
>
> 例如~\]\# useradd -s /bin/tcsh centos7  添加一个叫centos7的用户并指定它的shell为tcsh
>
> ## **搜索和查询类**
>
> **file命令**  查看文件内容类型
>
> 例如
>
> \[root@dxl /tmp 16:56:00\]\# file /etc/fstab
>
> /etc/fstab: ASCII text
>
> 可以知道fstab是一个标准的文本文件
>
> **type命令**  判断一个命令是外部命令还是内部命令
>
> 语法格式 type  COMMAND
>
> **help命令** 用于shell内部命令的帮助信息
>
> 语法格式 help COMMAND
>
> **man  命令   **帮助手册
>
> 语法格式 man COMMAND
>
> **Info命令**  在线获取命令帮助
>
> **which命令**  用于查找某个可执行的命令文件的位置
>
> 格式 which  命令名称
>
> 例如：
>
> \[root@dxl /tmp 17:13:02\]\# which passwd
>
> /usr/bin/passwd
>
> **whereis命令** 只能用于程序名的搜索，而且只搜索二进制文件  例如：whereis ls
>
> 语法格式whereis \[options\] name…
>
> 常用选项：
>
> -b:仅搜索二进制程序路径
>
> -m:仅搜索使用手册文件路径；
>
> **who命令**  识别当前登录的用户，显示关于 当前在本地系统上的所有用户的信息
>
> **w命令**  显示目前登入系统的用户信息
>
> **语　　法：**w \[-fhlsuV\]\[用户名称\]
>
> 常用选项：
>
> -f 　开启或关闭显示用户从何处登入系统。  
> -h 　不显示各栏位的标题信息列。  
> -l 　使用详细格式列表，此为预设值。  
> -s 　使用简洁格式列表，不显示用户登入时间，终端机阶段作业和程序所耗费的CPU时间。  
> -u 　忽略执行程序的名称，以及该程序耗费CPU时间的信息。  
> -V 　显示版本信息。
>
> **history命令  **命令历史是bash基础特性之一
>
> history命令默认最大的保存条数是1000条，存放在用户家目录下.bash\_history
>
> 控制history条数的环境变量:HISTSIZE 控制当前shell进程可保留的条数
>
> HISTFILESIZE:控制命令历史文件.bash\_history保存的条数
>
> HISTSIZE=100
>
> HISTFILESIZE=100  这两行追加到 当前用户家目录下的.bash\_profile 文件中就可以改变默认值，要是都设为零，那么久禁用了历史命令记录。
>
> #### **命令用法：**
>
> history -c 清除当前shell进程中的命令记录
>
> history -d offset:删除历史记录的第n条命令，例如:history -d5 删除第五条命令记录
>
> history -r:从历史文件列表到当前历史记录列表中
>
> history -w:
>
> #### **调用命令历史列表的命令**
>
> !!或ctrl+p :重复执行上一次命令
>
> !n :执行历史命令列表第n条命令，例如!5,执行命令列表第5条命令
>
> !STRING:执行命令历史列表中最近一个以STRING开头的命令。还可以输入Ctrl+R进行搜索。
>
> 小技巧：调用上一条命令的最后一个参数：
>
> 快捷键：ESC, .
>
> 字符串：!$
>
> 例如：我执行了ls /etc/sysconfig/network-scripts/ifcfg-eth后，然后在其他命令想再调用后面的参数/etc/sysconfig/network-scripts/ifcfg-eth ，先按下ESC键再按.  就会引用进来。很实用。
>
> ## **其它类**
>
> tty  显示当前终端  例如
>
> \[root@dxl ~ 12:45:49\]\# tty
>
> /dev/pts/0
>
> 伪终端是pty。
>
> 虚拟终端tty,centos7启动后默认有6个tty1–tty6,alt+F1-F6键切换
>
> 串行终端ttyS：用于串行试逐位数据传输，常见有25针9针连接器。
>
> 物理终端，控制台：console,
>
> **echo命令**  打印或输出内容,查询变量值，常用于编程
>
> \[root@dxl ~ 12:46:19\]\# echo $HISTSIZE
>
> 1000
>
> \[root@dxl ~ 18:13:37\]\# echo $HISTFILESIZE
>
> 1000
>
> 语 　 法：echo \[-ne\]\[字符串\]或 echo \[–help\]\[–version\]  
> 补充说明：echo会将输入的字符串送往标准输出。输出的字符串间以空白字符隔开, 并在最后加上换行号。  
> 参　　 数：-n 不要在最后自动换行  
> -e 若字符串中出现以下字符，则特别加以处理，而不会将它当成一般  
> 文字输出：  
> \a 发出警告声；  
> \b 删除前一个字符；  
> \c 最后不加上换行符号；  
> \f 换行但光标仍旧停留在原来的位置；  
> \n 换行且光标移至行首；  
> \r 光标移至行首，但不换行；  
> \t 插入tab；  
> \v 与\f相同；  
> \ 插入\字符；  
> \nnn 插入nnn（八进制）所代表的ASCII字符；  
> –help 显示帮助  
> –version 显示版本信息
>
> **export命令**   设置或显示环境变量。（比如我们要用一个命令，但这个命令的执行文件不在当前目录，这样我们每次用的时候必须指定执行文件的目录，麻烦，在代码中先执行export，这个相当于告诉程序，执行某某东西时，需要的文件或什么东东在这些目录里）
>
> **语　　法：**export \[-fnp\]\[变量名称\]=\[变量设置值\]  
> **补充说明：**在shell中执行程序时，shell会提供一组环境变量。 export可新增，修改或删除环境变量，供后续执行的程序使用。export的效力仅及于该此登陆操作。  
> **参　　数：**  
> -f 　代表\[变量名称\]中为函数名称。  
> -n 　删除指定的变量。变量实际上并未删除，只是不会输出到后续指令的执行环境中。  
> -p 　列出所有的shell赋予程序的环境变量。  
> 一个变量创建时，它不会自动地为在它之后创建的shell进程所知。而命令export可以向后面的shell传递变量的值。当一个shell脚本调用并执行时，它不会自动得到原为脚本（调用者）里定义的变量的访问权，除非这些变量已经被显式地设置为可用。export命令可以用于传递一个或多个变量的值到任何后继脚本。 —-《UNIX教程》
>
> **startx**  在虚拟终端接口输入命令 startx &，可以启动图像界面接口



