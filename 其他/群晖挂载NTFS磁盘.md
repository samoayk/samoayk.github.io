# 群晖挂载NTFS磁盘

# DS923+ 7.21
## One  
到了DSM7.X的年代，当你再去修改/etc.defaults/synoinfo.conf这个文件，你会发现修改的内容在系统重启后就没有办法保存下来。
## Two  
于是有不少网友就问博主：在DSM7.X怎样识别NTFS？
### 操作方法有两种，选择任意一个都可以：  
>第一种：先按照[本页图片](#pic1)计算出esataportcfg和internalportcfg两个参数对应的值，然后把参数写入user_config.json，重新编译DSM7.X的引导文件，用新的引导文件启动，就可以正常识别NTFS硬盘了。  
>第二种：如果你不会编译引导，可以用。---先不做引用（感觉不够牛逼）

# DS3617+ 6.23
## 开启群晖SSH功能
1. 控制面板
2. 终端机和SNMP
3. 终端机
4. 启动Telnet+启动SSH功能：全部打钩
## 登录群晖SSh
1. 启动Windows PowerShell/Terminal.app/终端
2. 键入以下命令并按 Enter 键：```ssh s@192.168.21.178 -p 22```
3. 输入 DSM/SRM 管理员帐户的密码。
4. 键入```sudo -i```并按 Enter 键。
5. 再次输入 DSM/SRM 管理员帐户的密码并按 Enter 键。
## 修改群晖磁盘及NTFS磁盘比例  
1. 输入：```vi /etc.defaults/synoinfo.conf```
2. 输入：```i```
1. 按图2修改图1红圈部分数据（磁盘数量对应群晖显示的磁盘排序）<a id="pic1"></a>  
![图1](https://wp.gxnas.com/wp-content/uploads/2018/07/20180222150454_98932.png)
![图2](https://wp.gxnas.com/wp-content/uploads/2018/07/20180222150454_21862.png)
## 改完后保存，退出重启群晖
1. 保存：```:wq```
1. 退出：```exit```
