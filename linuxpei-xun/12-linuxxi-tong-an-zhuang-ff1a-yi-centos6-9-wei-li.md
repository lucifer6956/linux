# 一：虚拟机VMware安装

windows下安装推荐使用 VMware Workstation Pro12.5版本

      下载网址：http://www.vmware.com/products/workstation/workstation-evaluation.htm

l[![](http://www.178linux.com/wp-content/uploads/2017/05/20170521194340_49051.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521194340_49051.png)

# 二： linux硬件资源分配

##         1：硬件分配

*       内存：1G
*       硬盘：200G
*       cpu：2核心
*       网络模式：仅主机模式及桥接模式全部开启
 
  ## 2：linux安装文件目录空间分配
*     /          根目录                  100G
*    /boot    系统内核文件         1G
*    /app      应用程序               50G
*    swap     交换分区               1G                                                 

          注意：所有的文件夹都在根目录下。/boot 以及 /app 文件夹虽然在

                  根目录下，但是其文件内容是放在其他的主分区内的。       

#  三：linux安装准备

*          1 在VMware上 点击“创建新的虚拟机”
*          2 安装模式   选择“典型”
*          3 安装来源  选择“稍后安装操作系统”
*          4 选择客户机操作系统
*             LINUX
*            Centos64
*          5 命名虚拟机
*            Centos7.3（安装的linux版本号为多少时，就选择相应的版本）
*            位置（选择Centos iso文件所在的文件夹）
*          6 指定磁盘容量 200G 单个文件
*          7 设置虚拟机硬件环境 内存 处理器 网卡信息
*            内存：1.3G
*            处理器：2核
*            网卡信息：仅主机模式、桥接模式都打开

# 四：Linux安装

     1 开启此虚拟机

             2 安装模式的选择

            install or upgrade an existing system  
            install system with basic vedio driver  
            rescue install system  
            第一项为正常安装  
            第二项为基本显卡安装  
            第三项为救援模式  
            选择第一项



* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521200315_46502.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521200315_46502.png)
*            3 检查硬件 故障  disc found
 
              此项主要检查安装光盘有无问题。选择检查，选择ok
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521200714_12485.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521200714_12485.png)
* 
*          4 语言选择  English
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521200802_63597.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521200802_63597.png)
*          5 键盘布局  English
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521200915_91819.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521200915_91819.png)
*           6 设备模式选择
 
               Basic storage Devices
 
               Specialized storage Devices
 
               第一项为本地安装 第二项为远程安装
 
               选择第一项
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521201003_50733.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521201003_50733.png)
* 
* 7 删除磁盘上的分区和文件系统，选Yes, discard any data
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521201216_83117.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521201216_83117.png)
*   8       Hostname与 Configure Network
 
               Hostme：根据自己习惯命名即可
 
               Configure network : 需要点掉 Connect automaictlly
 
               此项相当于开启网卡
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521201340_75119.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521201340_75119.png)
* 9 配置网卡信息（Configure Network）
*  打开自动连接（Connect automatically）
* 两个网卡 eth0 eth1都要打开
* 
* 
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521201839_17350.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521201839_17350.png)
*           10时区选择
*           在地图上选择上海shanghai
 
            select clock use utc 此选项卡勾掉，此选项为使用UTS时间
* 
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521202202_59377.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521202202_59377.png)
* 
*         11 设置root用户密码
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521202331_99308.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521202331_99308.png)
*           12 安装方式，选择自定义布局Create Custom Layout
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521202424_53391.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521202424_53391.png)
*           13 创建分区
 
               具体分区规划如下：
 
               分区     大小（GB）     大小（MB）
 
              /boot     1          1024
 
               /             100     102400
 
               /app     50     51200
 
               swap     2     2048
 
 
              注意：分区时在Standard partition 模式下进行分区
 
  硬盘模式（file system type）选择ext4
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521202910_36811.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521202910_36811.png)
  [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521202918_65000.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521202918_65000.png)
  [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521202930_94864.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521202930_94864.png)
  [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521202938_31450.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521202938_31450.png)
  [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521202945_44623.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521202945_44623.png)
  [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521202953_27720.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521202953_27720.png)
  [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521203002_47182.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521203002_47182.png)
*       14 格式化创建分区
*      格式化硬盘
* 
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521203317_37462.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521203317_37462.png)
* 
* 开始给硬盘分区
* 
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521203430_59306.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521203430_59306.png)
*    15选择安装包
 
                选择Desktop 然后在自定义选择 Customize now
 
                选择KDE
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521203703_50980.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521203703_50980.png)
  [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521203703_37521.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521203703_37521.png)
*       16进入安装界面，开始安装安装包
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521203902_59396.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521203902_59396.png)
* 
* 17 安装完成后，点击reboot重启
* 
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521204011_94779.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521204011_94779.png)
* 
* 18  重启后进入欢迎界面，点击Fword
* 
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521204145_75934.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521204145_75934.png)
* 
* 19 同意协议，下一步
* 
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521204256_58454.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521204256_58454.png)
* 
* 20 创建自己的用户名及密码
* 21 设置时间
* 22 开启Kdump。选择NO,不然将要重启系统
* 
* [![](http://www.178linux.com/wp-content/uploads/2017/05/20170521204916_56151.png)](http://www.magedu.com/wp-content/uploads/2017/05/20170521204916_56151.png)

23 安装OK

