# 群晖挂载NTFS磁盘

# RS1619xs+ 7.2.1-69057
操作方法有两种，选择任意一个都可以：
## One  
以RR引导为例；先按照[本页图片](#pic1)计算出esataportcfg和internalportcfg两个参数对应的值，然后在选择型号、选择版本、解析pat后**设置synoinfo**，重新编译DSM7.X的引导文件，用新的引导文件启动，就可以正常识别NTFS硬盘了。 
## Two  
如果你不会编译引导，可以用。
  >- 共享文件夹（随意挂载内容不占用空间）-新建一个文件夹（4T）-记录下这个文件夹位置：/volume1/sk/4T
  >- 查看需要挂载的NTFS磁盘盘位sata3，几个分区p1
  >- 控制版面-任务计划-新增-触发的任务-用户定义的脚本-常规-任务名称：test、用户账号：root-任务设置-用户定义的脚本：mount -t ntfs /dev/sata3p1 /volume1/sk/4T-确定

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
