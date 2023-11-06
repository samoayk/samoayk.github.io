# 群晖挂载NTFS磁盘
## Putty登录群晖
1. IP地址
1. 进入后输入管理员账号
1. 输入管理员密码
1. 进入root模式：```sudo -i```
1. 输入：```vi /etc.defaults/synoinfo.conf```
## 修改群晖磁盘及NTFS磁盘比例  
按图2修改图1红圈部分数据（磁盘数量对应群晖显示的磁盘排序）
![图1](https://wp.gxnas.com/wp-content/uploads/2018/07/20180222150454_98932.png)
![图2](https://wp.gxnas.com/wp-content/uploads/2018/07/20180222150454_21862.png)
## 改完后保存，退出重启群晖
- 保存：```:wq```
- 退出：```exit```
