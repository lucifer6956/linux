既然知道了如何在Linux系统中创建目录，接下来你可能会想在这些目录中创建一些文件，可以使用 touch 命令。

  


  


需要注意的是，touch 命令不光可以用来创建文件（当指定操作文件不存在时，该命令会在当前位置建立一个空文件），此命令更重要的功能是修改文件的时间参数（但当文件存在时，会修改此文件的时间参数）。

  


  


Linux 系统中，每个文件主要拥有 3 个时间参数（通过 stat 命令进行查看），分别是文件的访问时间、数据修改时间以及状态修改时间：

* 访问时间（Access Time，简称 atime）：只要文件的内容被读取，访问时间就会更新。例如，使用 cat 命令可以查看文件的内容，此时文件的访问时间就会发生改变。
* 数据修改时间（Modify Time，简称 mtime）：当文件的内容数据发生改变，此文件的数据修改时间就会跟着相应改变。
* 状态修改时间（Change Time，简称 ctime）：当文件的状态发生变化，就会相应改变这个时间。比如说，如果文件的权限或者属性发生改变，此时间就会相应改变。

  


touch 命令的基本格式如下：

\[root@localhost ~\]\# touch \[选项\] 文件名

选项：

* -a：只修改文件的访问时间；
* -c：仅修改文件的时间参数（3 个时间参数都改变），如果文件不存在，则不建立新文件。
* -d：后面可以跟欲修订的日期，而不用当前的日期，即把文件的 atime 和 mtime 时间改为指定的时间。
* -m：只修改文件的数据修改时间。
* -t：命令后面可以跟欲修订的时间，而不用目前的时间，时间书写格式为 `YYMMDDhhmm`。

  


可以看到，touch 命令可以只修改文件的访问时间，也可以只修改文件的数据修改时间，但是不能只修改文件的状态修改时间。因为，不论是修改访问时间，还是修改文件的数据时间，对文件来讲，状态都会发生改变，即状态修改时间会随之改变（更新为操作当前文件的真正时间）。

  


  


【例 1】 touch 命令创建文件。

\[root@localhost ~\]\#touch bols  
\#建立名为 bols 的空文件

  


【例 2】 在例 1 的基础上修改文件的访问时间。

\[root@localhost ~\]\#ll --time=atime bols  
\#查看文件的访问时间  
-rw-r--r-- 1 root root 0 Sep 25 21:23 bols  
\#文件上次的访问时间为 9 月 25 号 21：23  
\[root@localhost ~\]\#touch bols  
\[root@localhost ~\]\#ll --time=atime bols  
-rw-r--r-- 1 root root 0 May 15 16:36 bols  
\#而如果文件已经存在，则也不会报错，只是会修改文件的访问时间。

  


【例 3】 修改 bols 文件的 atime 和 mtime。

\[root@localhost ~\]\# touch -d "2017-05-04 15:44" bols  
\[root@localhost ~\]\# ll bols; ll --time=atime bols; ll --time=ctime bols  
-rw-r--r-- 1 root root 0 May 4 2017 bols  
-rw-r--r-- 1 root root 0 May 4 2017 bols  
-rw-r--r-- 1 root root 0 Sep 25 21:40 bols  
\#ctime不会变为设定时间，但更新为当前服务器的时间

