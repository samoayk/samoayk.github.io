[Kodi+NAS打造家庭影音娱乐中心](https://www.zhihu.com/tardis/zm/art/264883864?source_id=1005)
==================================================================================

共 2516 字阅读需 10.5 分钟

到目前为止对NAS的需求并不高，比如大佬们非常看重的外网访问，文件云端同步等没有需求，就是简单的作为网络存储介质，单纯的存储家庭照片以及下载的高清电影纪录片等，可以在家庭局域网访问。

1.网络拓扑
------

![](https://pica.zhimg.com/v2-3186cd1860ebb6a2eed45478b8186086_1440w.webp?consumer=ZHI_MENG)

注意的几点：

1.电视最好是通过网线连接交换机，无线不稳定

2.NAS、电视、电脑要在一个网段（如图中绿色所示，ip不是真实ip，请以自家交换机ip为准），不然电视播放NAS上的大文件基本不可能。最开始的时候NAS连光猫的网口，电视连AP，两者不在一个网段，虽然在电视上可以看到文件目录，但根本无法播放大文件。

家里的配置：

无线AP+AC是TPLINK的套装，网线在装修的时候预埋，最好是每个房间预留一个网口。采用AP+AC的好处是不需要购买多个路由器，避免了路由器布线和供电的问题，此外可以无缝切换网络。

网线秋叶原六类线，网口和网线一开始一定要规划好，一旦装修完后面升级很难了。

  
**2.NAS操作**

威联通入门的ts428，四盘位不带硬盘。

硬盘是希捷酷狼，先入了一块8T。

威联通的官网及使用手册，官网的使用手册已经比较详细了。

官网：[威联通科技股份有限公司(QNAP Systems, Inc.) - 网络存储装置(NAS)](https://link.zhihu.com/?target=https%3A//www.qnap.com.cn/zh-cn)

使用手册：[https://docs.qnap.com/nas/QTS4.3.4/sc/](https://link.zhihu.com/?target=https%3A//docs.qnap.com/nas/QTS4.3.4/sc/)

贴一下使用手册的界面，首先要做的就是配置，访问NAS，红框中是教程。

![](https://pica.zhimg.com/v2-352667e9ef8e515446e0ad77c3db35b4_1440w.webp?consumer=ZHI_MENG)

1.威联通TS-428由于硬件的限制，目前还没找到通过docker安装迅雷的方法，这一点对于下载来说是硬伤

2.**威联通配置好之后一定要开通ftp服务，后面会用到！！！！**

如果预算高，可以选用威联通的高配或者群辉

群辉

3.电视操作
------

电视机是19年国庆节期间买的索尼9000f，现已停产，替代品9000H。除了大法的传统技能，与友商相比还没有广告

其他的品牌，TCL雷鸟R625C这款的北美型号R625，在国外的口碑很好。复刻到了国内销售

创维在山姆会员店看过机器，还是不错的。

小米和华为就品牌而言已经自带流量了，尤其是菊花厂最近因为川大统领的骚操作，更是引起了国内人民的支持。这两款网上有很多评测。

以下是针对索尼电视的操作，其他品牌的电视类似。

1.索尼预装的应用市场是当贝市场的阉割版，很多好用的软件都没上架，所以需要一个U盘，下载当贝的完整版 [http://www.dangbei.com/apps/](https://link.zhihu.com/?target=http%3A//www.dangbei.com/apps/) 到U盘中，将U盘插到电视上。在主页打开【应用助手】，然后找到第三方软件的apk安装包，打开并确认安装即可。

2.安装完整版当贝助手之后，搜索小白文件管理器，下载安装。主要是用小白文件管理器的ftp功能将电视搞成一台ftp服务器，从可以方便的将一些文件，比如apk，zip文件包，json xml配置文件等上传到电视上，此外还可以安装上传的apk。按照下面的步骤打开小白文件管理器

![](https://pic4.zhimg.com/v2-69307873598415a0e4b10ce000fcc8fd_1440w.webp?consumer=ZHI_MENG)

![](https://pic3.zhimg.com/v2-fe28b027ff3d9938132f5f556186900e_1440w.webp?consumer=ZHI_MENG)

![](https://pica.zhimg.com/v2-58f69e4ba5ca61c63facfb1498121baa_1440w.webp?consumer=ZHI_MENG)

按照上面说明，在自己的电脑打开ftp。

3.Kodi-实现高清影视点播
---------------

1.安装Kodi

当贝市场中是有kodi的，但19.x版本强制使用python3 的库，很多插件是无法安装的。因此需要安装18.x版本，下载地址：[http://mirrors.kodi.tv/releases/android/arm64-v8a/kodi-18.8-Leia-arm64-v8a.apk](https://link.zhihu.com/?target=http%3A//mirrors.kodi.tv/releases/android/arm64-v8a/kodi-18.8-Leia-arm64-v8a.apk)。将在pc上下载的apk可以通过步骤2中的ftp传到电视上，然后通过小白文件管理器安装。

2.启动Kodi，配置语言。

![](https://picx.zhimg.com/v2-9177c5e7e5695c47b1a2086f1db65309_1440w.webp?consumer=ZHI_MENG)

![](https://pic3.zhimg.com/v2-234a78a0ee5d781ea6faa1e1bbe842fc_1440w.webp?consumer=ZHI_MENG)

**首先点击skin选项卡，fonts----->选择Arial based，很重要，一定要做这一步，不然全屏的乱码**

![](https://picx.zhimg.com/v2-f495a6cd715dc39bc338515c79ce2649_1440w.webp?consumer=ZHI_MENG)

![](https://pic4.zhimg.com/v2-e858cb401cc4c1b914c1d9b5d9cccd47_1440w.webp?consumer=ZHI_MENG)

然后点击regional 选择Language ,选中chinese(Simple) 简体中文，**切记，做这一步，一定要再选择fonts之后**

![](https://pica.zhimg.com/v2-8eecfc3ee6fcc8fcceb804ec0dbeeb76_1440w.webp?consumer=ZHI_MENG)

![](https://pic3.zhimg.com/v2-4a05d2eb251d119e72d6736dec287be4_1440w.webp?consumer=ZHI_MENG)

第2步完成之后：

![](https://pic3.zhimg.com/v2-88ea7037077c8828d6ec84c487affc50_1440w.webp?consumer=ZHI_MENG)

3.安装插件

Kodi安装插件的过程 [Kodi添加安装插件教程 - kodi插件 - kodi中文网](https://link.zhihu.com/?target=http%3A//www.kodiplayer.cn/plugins/2861.html)

比较基础的两个插件：

1）更换软件源：更换为清华镜像: [https://pan.baidu.com/s/17dOj4qvBwg86k9dt879gVA](https://link.zhihu.com/?target=https%3A//pan.baidu.com/s/17dOj4qvBwg86k9dt879gVA)

提取码: rdee 。

2）字幕库：[https://n459.com/file/15911488-460911694](https://link.zhihu.com/?target=https%3A//n459.com/file/15911488-460911694)

将这两个插件zip包下载到电脑上，然后通过步骤2中的小白文件管理器上传到电视上，再通过Kodi的从zip文件安装。

![](https://pic2.zhimg.com/v2-faa119279b8c11822b45fc8b6a9cfdb7_1440w.webp?consumer=ZHI_MENG)

4.Kodi连接nas

从网上一些用户使用来看，在播放大文件的时候ftp协议相比其他协议卡顿率较低，传输速率高，如何配置ftp？

以主界面“电影”为例 -> 进入文件区

![](https://pica.zhimg.com/v2-b7cb3bc9cfbe9356684debd036592f2c_1440w.webp?consumer=ZHI_MENG)

添加视频 -> 浏览

![](https://pic2.zhimg.com/v2-d6fadae56d64919edd3038f75fc2dc55_1440w.webp?consumer=ZHI_MENG)

添加网络位置

![](https://pic2.zhimg.com/v2-09a5e4bcd3f39f8ced129618736ade03_1440w.webp?consumer=ZHI_MENG)

协议选用“FTP服务器”

![](https://pic1.zhimg.com/v2-bd7a04750638d95f0cde13a5f025162a_1440w.webp?consumer=ZHI_MENG)

输入ftp的地址，用户名和密码，确定，选中刚建好的ftp协议服务器

![](https://pica.zhimg.com/v2-6ecd939e993c3e2b6e3a7ce9570286ba_1440w.webp?consumer=ZHI_MENG)

然后选中一个文件夹，确定就可以了。

![](https://pica.zhimg.com/v2-7aeba96a7d6fc7f65f528094d56bca7c_1440w.webp?consumer=ZHI_MENG)

点击确定

![](https://pic3.zhimg.com/v2-f5b333f18eb8852dfba5a21aa3b5e80e_1440w.webp?consumer=ZHI_MENG)

设定内容－该目录包涵“电影“，然后就可以使用电影刮削器了。

![](https://pic3.zhimg.com/v2-5cb043331d3684d32d647c91252a6748_1440w.webp?consumer=ZHI_MENG)

设定内容－获取更多－“豆瓣电影刮刮器”（如果安装的话）

![](https://pic4.zhimg.com/v2-ce00300243f357bbd91c1e675da461af_1440w.webp?consumer=ZHI_MENG)

最终是这个效果

![](https://pica.zhimg.com/v2-17b97b27c1c2cc484de68d143a25cf50_1440w.webp?consumer=ZHI_MENG)

![](https://pic4.zhimg.com/v2-c8fd07fe2c2ab0e6cc3bfd4b12435979_1440w.webp?consumer=ZHI_MENG)

4.电脑操作
------

由于威联通ts428上无法安装迅雷，因此用家用电脑通过迅雷下载，下载完之后通过ftp传输到NAS上，当然也可以通过移动硬盘直接挂到NAS上。

电脑需要安装的软件：

1)迅雷，有些同学可能很反感迅雷，但现在的网络环境下，迅雷是下载bt资源最多速度最快的软件了，如果已经收集好了一大批种子，可以开一个月会员集中下载。

2)[FileZilla中文网 - 免费开源的FTP解决方案](https://link.zhihu.com/?target=https%3A//www.filezilla.cn/)，FIleZilla安装好之后配置ftp，连接【2NAS操作】中NAS的ftp。注意不要与【3电视操作】中的小白文件管理器的ftp混了

然后就是迅雷不停下载，下载完了之后就通过ftp传到NAS上。

\>由 \[Circle 阅读助手\](https://circlereader.com) 生成
