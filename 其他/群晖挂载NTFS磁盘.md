# 群晖挂载NTFS磁盘
## 开启群晖SSH功能
1. 控制面板
2. 终端机和SNMP
3. 终端机
4. 启动Telnet+启动SSH功能：全部打钩
## 登录群晖SSh
1. Putty登录
  1. IP地址
  1. 进入后输入管理员账号
  1. 输入管理员密码
  1. 进入root模式：```sudo -i```
  2. 再次输入管理员密码
1. 在 Windows 10、macOS 或 Linux 上登录
  1.在计算机上启动终端应用程序：
    - Windows 10：Windows PowerShell
    - macOS：Terminal.app
    - Linux：终端
   1. 键入以下命令并按 Enter 键： ssh XX@10.17.2.6 -p 22
   2. 输入 DSM/SRM 管理员帐户的密码。
   3. 键入 sudo -i 并按 Enter 键。
   4. 再次输入 DSM/SRM 管理员帐户的密码并按 Enter 键。
## 修改群晖磁盘及NTFS磁盘比例  
1. 输入：```vi /etc.defaults/synoinfo.conf```
2. 输入：i
1. 按图2修改图1红圈部分数据（磁盘数量对应群晖显示的磁盘排序）
![图1](https://wp.gxnas.com/wp-content/uploads/2018/07/20180222150454_98932.png)
![图2](https://wp.gxnas.com/wp-content/uploads/2018/07/20180222150454_21862.png)
## 改完后保存，退出重启群晖
- 保存：```:wq```
- 退出：```exit```
