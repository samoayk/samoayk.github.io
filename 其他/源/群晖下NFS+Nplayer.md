[群晖下NFS与手机端播放器还可以这样用？！](https://post.smzdm.com/p/a5odzznk/)
===========================================================

共 1535 字阅读需 6.5 分钟

2022-12-07 11:13:46 21点赞 161收藏 21评论

开篇想说：  

--------

一看头图我猜想大家就知道了，我说的[播放器](https://www.smzdm.com/ju/s2yw8m2/)就是nPlayer，上篇文章的时候也有网友指出用的就是这个播放器，之所以上次没放出来，也是因为它比较强大值得我单独多说几句。这款软件可以说是功能上的集大成者；Webdav/Nfs/ftp/smb 这些主流协议都支持，横跨windows和Unix系统（苹果其实也是unix）。dolby和DTS不在话下，就连音频格式也都兼容，这是要抢[音乐播放](https://www.smzdm.com/ju/s23k5w2/)器的饭碗啊！开个玩笑，音乐播放器还是得找专门的app来的专业。

插入一下上篇文章地址：

文章

![](https://qna.smzdm.com/202212/02/6389cb85e71664487.jpg_a200.jpg)

手机上支持群晖的好用播放器有这些！

![](https://avatarimg.smzdm.com/default/4545427623/638381f7203424067-small.jpg)糖炒麦芽糖味阿斯巴甜![](https://res.smzdm.com/images/certificate/ordinary_life_medal.png)

2022-12-04

![](https://res.smzdm.com/wx_images/zan.png)

23

看看Nplayer的宣传语
-------------

人家说得出确实做得到，程序员很牛！30多兆的app实现这么多功能比起来我们某些国产app动辄200M的安装包，让人致敬！

[![](https://am.zdmimg.com/202212/06/638f385e9d2162256.jpg_e1080.jpg)](https://post.smzdm.com/p/a5odzznk/pic_2/)

[![](https://qnam.smzdm.com/202212/06/638f385f09704213.jpg_e1080.jpg)](https://post.smzdm.com/p/a5odzznk/pic_3/)

[![](https://qnam.smzdm.com/202212/06/638f385de48f43955.jpg_e1080.jpg)](https://post.smzdm.com/p/a5odzznk/pic_4/)

说说使用
----

可能大家都说这有多难，还能不会用？一般来说我也不写口水文章的，多少得有点货吧！开篇题目说的NFS可能很多很多初入NAS的朋友都一头雾水。我简单科普下：一般来说win下用smb，linux/unix下使用NFS。

NFS 为网络文件系统 (Network file system)的缩写,由Sun公司开发,通过网络,NFS支持在不同的文件系统之间共享文件.用户不必关心计算机的型号,以及使用的操作系统,如果想使用远程计算机上的文件,只要用mount命令将远程的目录挂接在本地文件系统下,就可以如同使用本地文件一样使用这个资源。由于是内核直接支持，部署简单、运行稳定，协议简单，所以传输效率高。NFS 的缺点是没有加密授权等功能，仅依靠 IP 地址或[主机](https://www.smzdm.com/ju/sp3rz02/)名来决定用户能否使用。

SMB在Linux上也有实现，不是不能用。但是实际效果来说要慢一些，特别是现在的智能电视基本都是SMB连接，速度好不好大家是有判断的。WebDAV的优缺点主要是基于http协议，有文件io锁支持版本控制，如果放在播放器里有些大材小用。

我举例子的这个np大版本是1.7，没有用最新版。作为软件从业人员上了岁数以后其实没那么喜欢折腾了，喜欢稳定压倒一切。日后有空再看看新版在哪些方面有优势。  

第一步：简单的我不赘述，安装后左上角有一个无线标志，点进去看下自己的IP地址。本人地址为192.168.3.96为例。  

[![](https://am.zdmimg.com/202212/06/638f385fc12d86939.jpg_e1080.jpg)](https://post.smzdm.com/p/a5odzznk/pic_5/)获取ip

返回点击加号，选择新建[服务器](https://www.smzdm.com/fenlei/fuwuqi/)，类型选择NFS。

[![](https://am.zdmimg.com/202212/06/638f3ea7da316759.jpg_e1080.jpg)](https://post.smzdm.com/p/a5odzznk/pic_6/)

第二步：在弹出的对话框中，输入你的nas地址，然后确定。糟糕怎么没权限呢？继续往下看。

[![](https://qnam.smzdm.com/202212/06/638f385fa2dac5377.jpg_e1080.jpg)](https://post.smzdm.com/p/a5odzznk/pic_7/)

第三步：最重要的一点就是nfs是需要Kerberos鉴权认证的，需要在[群晖](https://pinpai.smzdm.com/2315/)配置；果断打开群晖控制面板，进入共享文件夹。这有个前提:你的群晖nas要在文件服务中开启NFS。

选择你的文件夹  

[![](https://qnam.smzdm.com/202212/06/638f385b3785a4321.png_e1080.jpg)](https://post.smzdm.com/p/a5odzznk/pic_8/)

点击编辑 - 按我的推荐填写，注意ip地址不要抄作业，要写你第一步获取的ip。

[![](https://qnam.smzdm.com/202212/06/638f385b3e6185560.png_e1080.jpg)](https://post.smzdm.com/p/a5odzznk/pic_9/)

确认两次

[![](https://qnam.smzdm.com/202212/06/638f385b38764932.png_e1080.jpg)](https://post.smzdm.com/p/a5odzznk/pic_10/)

最后一步：返回nPlayer测试一下你的配置吧！如果没问题就应该顺利开启。

[![](https://qnam.smzdm.com/202212/06/638f385fca9211649.jpg_e1080.jpg)](https://post.smzdm.com/p/a5odzznk/pic_11/)

总结  

-----

折腾20分钟你问我为啥不用SMB？我说用NFS有逼格也好，速度快也罢，终归我们在折腾和玩中又多学了一个技能！知识这个事情触类旁通，不论你我做什么行业，往往路越往后走，决定高度的除了专业能力还有我们知识图谱的广度。

祝大家玩的开心。  

作者声明本文无利益相关，欢迎值友理性交流，和谐讨论～

![](https://res.smzdm.com/pc/pc_shequ/dist/img/the-end.png)

NAS存储

糖炒麦芽糖味阿斯巴甜

\>由 \[Circle 阅读助手\](https://circlereader.com) 生成
