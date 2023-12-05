# 群晖挂载NTFS磁盘
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
1. 按图2修改图1红圈部分数据（磁盘数量对应群晖显示的磁盘排序）
![图1](https://wp.gxnas.com/wp-content/uploads/2018/07/20180222150454_98932.png)
![图2](https://wp.gxnas.com/wp-content/uploads/2018/07/20180222150454_21862.png)
## 改完后保存，退出重启群晖
1. 保存：```:wq```
1. 退出：```exit```
