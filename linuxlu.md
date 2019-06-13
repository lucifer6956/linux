## Linux理论基础 {#linux理论基础}

* * Linux理论基础
    * 1. 计算机的组成及其功能
      2. \(1\) CPU（控制器和运算器）
      3. \(2\) 存储器
      4. \(3\) 输入设备
      5. \(4\) 输出设备
    * 1. Linux常见发行版，及不同发行版之间的联系与区别
      2. Linux内核和Linux发行版的关系
      3. Linux常见发行版
      4. Linux发行版之间的关系
      5. Linux发行版分类
      6. linux各发行版特点
    * 1. Linux的哲学思想

### 1. 计算机的组成及其功能 {#1-计算机的组成及其功能}

**冯.诺伊曼体系中，计算机有五大基本部件：控制器、运算器、存储器、输入设备、输出设备。**  
**实际应用中，计算机包括CPU（控制器和运算器）、存储器（Memory内存和Disk外存）、Input输入设备、Output输出设备。**

[![](http://www.178linux.com/wp-content/uploads/2018/03/1-3.png "1")](http://www.178linux.com/wp-content/uploads/2018/03/1-3.png)

#### \(1\) CPU（控制器和运算器） {#1-cpu控制器和运算器}

CPU由运算器、控制器、寄存器、缓存、指令集组成。  
a、运算器是实现算术运算和逻辑运算的部件：  
主要由算术逻辑部件（ALU：Arithmetic and Logic Unit）、寄存器组和状态寄存器组成：  
ALU主要完成对二进制信息的定点算术运算、逻辑运算和各种移位操作；  
通用寄存器组是用来保存参加运算的操作数和运算的中间结果；  
状态寄存器在不同的机器中有不同的规定，程序中，状态位通常作为转移指令的判断条件。  
b、控制器是计算机的指挥系统，通过地址来访问存储器（内存），从存储器中取出指令，经译码器分析后，根据指令分析结果产生相应的操作控制信号作用于其他部件，使得各部件在控制器控制下有条不紊地协调工作。  
控制器一般包括指令控制逻辑、时序控制逻辑、总线控制逻辑、中断控制逻辑等几个部分：  
指令控制逻辑要完成取指令、分析指令和执行指令的操作；  
时序控制逻辑要为每条指令按时间顺序提供应有的控制信号，一般时钟脉冲就是最基本的时序信号，是整个机器的时间基准，称为机器的主频；  
总线逻辑是为多个功能部件服务的信息通路的控制电路，就CPU而言一般分为内部总线和CPU对外联系的外部总线，外部总线有时候又叫做系统总线、前端总线（FSB）等；  
中断是指计算机由于异常事件，或者一些随机发生需要马上处理的事件，引起CPU暂时停止现在程序的执行，转向另一服务程序去处理这一事件，处理完毕再返回原程序的过程。由机器内部产生的中断，把它叫做陷阱（内部中断），由外部设备引起的中断叫外部中断。  
c、寄存器\(register\)是CPU内部用来存放数据的一些小型的存储区域，用来暂时存放参与运算的数据以及运算结果。寄存器由电子线路组成，存取速度非常快，与CPU的速度相当，寄存器的成本较高，因而数量较少。CPU内部的寄存器类型有指令寄存器、程序计数器、数据寄存器、地址寄存器以及状态寄存器等。

#### \(2\) 存储器 {#2-存储器}

a、Memory内存，RAM（Random Access Memory）  
由Cell存储单元组成，每个Cell为8bits。  
扩展思考：  
32位CPU能引用的存储单元位置，决定了最大可用到的内存大小为4GB：  
32位CPU，能够识别的存储单元地址个数位2^32个，每个位置代表一个存储单元Cell，每个Cell是8bits（1Byte），  
能用到的内存大小为2^32Bytes=4GB。  
b、Disk外存，即磁盘，存储数据。

#### \(3\) 输入设备 {#3-输入设备}

下指令，提供数据等。

#### \(4\) 输出设备 {#4-输出设备}

输出数据加工后的结果。

### 2. Linux常见发行版，及不同发行版之间的联系与区别 {#2-linux常见发行版及不同发行版之间的联系与区别}

#### Linux内核和Linux发行版的关系 {#linux内核和linux发行版的关系}

Linux内核指的是一个由Linus Torvalds负责维护，提供硬件抽象层、硬盘及文件系统控制及多任务功能的系统核心程序。  
Linux发行版就是由Linux内核与各种常用软件的集合产品，如今全球大约有数百款的Linux发行版本。

[![](http://www.178linux.com/wp-content/uploads/2018/03/无标题.png "无标题")](http://www.178linux.com/wp-content/uploads/2018/03/无标题.png)

#### Linux常见发行版 {#linux常见发行版}

**Linux发行版有三大主流分支：Debian、Slackware、Redhat，包含的主要发行版分别如下：**

1. Debian

   * Ubuntu

     Linux mint

   * Knopix

2. Slackware

   * S.u.S.E

     SLES-SuSE Linux Enterprise

     OpenSuSE

3. Redhat

   * RHEL-RedHat Enterprise Linux

     CentOS-Community ENTerprise

   * Fedore Core

**除了三大主流分支，还有两种比较流行的发行版：**

1. Gentoo
2. ArchLinux

[![](http://www.178linux.com/wp-content/uploads/2018/03/3-3.png "3")](http://www.178linux.com/wp-content/uploads/2018/03/3-3.png)

#### Linux发行版之间的关系 {#linux发行版之间的关系}

* Fedora是基于RHEL，CentOS，Scientific Linux, 和Oracle Linux的社区版本。相比RHEL，Fedora打包了显著的更多的软件包。其中一个原因是，多样化的社区参与Fedora的建设;它不只是一家公司。在这个过程中，CentOS用于活动，演示和实验，因为它是对最终用户免费提供的，并具有比Fedora的一个更长的发布周期\(通常每隔半年左右发布一个新版本\)。
* SUSE, SUSE Linux Enterprise Server \(SLES\), 和openSUSE 之间的关系类似于 Fedora, Red Hat Enterprise Linux, 和CentOS的关系。
* Debian是包括Ubuntu在内许多发行版的上游，而Ubuntu又是Linux Mint及其他发行版的上游。Debian在服务器和桌面电脑领域都有着广泛的应用。Debian是一个纯开源计划并着重在一个关键点上，稳定性。它同时也提供了最大的和完整的软件仓库给用户。

#### Linux发行版分类 {#linux发行版分类}

**Linux发行版都是基于同一内核，所以除了外观和名字不一样外，其他地方的区别不是很大，按用途大致分为桌面版和企业版：**

1. 桌面版：

   Ubuntu、Debian、Fedora、CentOS、openSUSE等。由于安装了图像界面，界面美观、操作方便，比较适合新手，但相对于企业版来说较消耗资源。

2. 企业版：

   RHEL、CentOS、Debian、Ubuntu、openSUSE、SLES等。系统稳定性好，资源消耗较小，满足企业需求，但基本都是命令行界面，需要有一定的基础才能上手操作。

**按照维护方式分为两类，一类是商业公司维护的发行版本，一类是社区组织维护的发行版本，前者以著名的Redhat\(RHEL\)为代表，后者以Debian为代表。**

1. 商业公司维护：

   RHEL、CentOS、SLES等

2. 社区组织维护：

   Debian、Ubuntu等

#### linux各发行版特点 {#linux各发行版特点}

**各发行版的思想，如图：**

[![](http://www.178linux.com/wp-content/uploads/2018/03/4-4.png "4")](http://www.178linux.com/wp-content/uploads/2018/03/4-4.png)

* **Redhat，应该称为Redhat系列，包括RHEL\(Redhat Enterprise Linux，也就是所谓的Redhat Advance Server，收费版本\)、Fedora Core\(由原来的Redhat桌面版本发展而来，免费版本\)、CentOS\(RHEL的社区克隆版本，免费\)。**
  Redhat应该说是在国内使用人群最多 的Linux版本，甚至有人将Redhat等同于Linux，而有些老鸟更是只用这一个版本的Linux。所以这个版本的特点就是使用人群数量大，资料非 常多，言下之意就是如果你有什么不明白的地方，很容易找到人来问，而且网上的一般Linux教程都是以Redhat为例来讲解的。Redhat系列的包管理方式采用的是基于**RPM包的YUM包管理方式**，包分发方式是编译好的二进制文件。稳定性方面RHEL和CentOS的稳定性非常好，适合于服务器使用， 但是Fedora Core的稳定性较差，最好只用于桌面应用。
* **Debian，或者称Debian系列，包括Debian和Ubuntu等。**  
  Debian是社区类Linux的典范，是迄今为止最遵循GNU规范 的Linux系统。Debian最早由Ian Murdock于1993年创建，分为三个版本分支\(branch\)： stable, testing 和 unstable。其中，unstable为最新的测试版本，其中包括最新的软件包，但是也有相对较多的bug，适合桌面用户。testing的版本都经 过unstable中的测试，相对较为稳定，也支持了不少新技术\(比如SMP等\)。而stable一般只用于服务器，上面的软件包大部分都比较过时，但是 稳定和安全性都非常的高。Debian最具特色的是**apt-get / dpkg包管理方式**，其实Redhat的YUM也是在模仿Debian的APT方式，但在二进制文件发行方式中，APT应该是最好的了。Debian的资料也很丰富，有很多支持的社区，有问题求教也有地方可去:\)

  Ubuntu严格来说不能算一个独立的发行版本，Ubuntu是基于Debian的unstable版本加强而来，可以这么说，Ubuntu就是 一个拥有Debian所有的优点，以及自己所加强的优点的近乎完美的 Linux桌面系统。根据选择的桌面系统不同，有三个版本可供选择，基于Gnome的Ubuntu，基于KDE的Kubuntu以及基于Xfc的 Xubuntu。特点是界面非常友好，容易上手，对硬件的支持非常全面，是最适合做桌面系统的Linux发行版本。

* **Gentoo，伟大的Gentoo是Linux世界最年轻的发行版本，正因为年轻，所以能吸取在她之前的所有发行版本的优点，这也是Gentoo 被称为最完美的Linux发行版本的原因之一。**  
  Gentoo最初由Daniel Robbins\(FreeBSD的开发者之一\)创建，首个稳定版本发布于2002年。由于开发者对FreeBSD的熟识，所以Gentoo拥有媲美 FreeBSD的广受美誉的ports系统 ——  
  **Portage包管理系统**。

  不同于APT和YUM等二进制文件分发的包管理系统，Portage是基于源代码分发的，必须编译后才能运行，对于大型软 件而言比较慢，不过正因为所有软件都是在本地机器编译的，在经过各种定制的编译参数优化后，能将机器的硬件性能发挥到极致。Gentoo是所有Linux 发行版本里安装最复杂的，但是又是安装完成后最便于管理的版本，也是在相同硬件环境下运行最快的版本。

* 最后，介绍一下**FreeBSD**，需要强调的是：  
  **FreeBSD并不是一个Linux系统!但FreeBSD与Linux的用户群有相当一部分是重合的，二者支持的硬件环境也比较一致，所采用的软件也比较类似，所以可以将FreeBSD视为一个Linux版本来比较。**

  FreeBSD拥有两个分支： stable和current。顾名思义，stable是稳定版，而 current则是添加了新技术的测试版。FreeBSD采用Ports包管理系统，与Gentoo类似，基于源代码分发，必须在本地机器编后后才能运 行，但是Ports系统没有Portage系统使用简便，使用起来稍微复杂一些。FreeBSD的最大特点就是稳定和高效，是作为服务器操作系统的最佳选 择，但对硬件的支持没有Linux完备，所以并不适合作为桌面系统。

### 3. Linux的哲学思想 {#3-linux的哲学思想}

**1. 一切皆文件**  
把几乎所有资源统统抽象为文件形式，包括硬件设备，甚至通信接口等，便于统一管理和定义；  
_对文件的操作有：open，read，write，close，delete，create_  
**2. 由众多功能单一的程序组成**  
一个程序只做一件事，并且做好，保证了Linux内核的高效运行；  
**3. 组合小程序完成复杂任务**  
通过连接多个简单的程序实现复杂的功能；  
**4. 尽量避免和用户交互**  
更贴近编程，易于以编程的方式实现自动化任务；  
**5. 使用文本文件保存配置信息**  
修改配置信息只需要任意一款文本编辑器就可以进行。

