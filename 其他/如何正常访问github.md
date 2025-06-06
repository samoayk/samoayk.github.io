Welcome to GitHub
-----------------

由于某些原因，国内访问Github会异常缓慢，在clone仓库时甚至只有10k以下的速度，下载半天有时还会失败需要从头再来，甚是让人恼火。 本文介绍通过修改系统hosts文件的办法，绕过国内dns解析，直接访问GitHub的CDN节点，从而达到加速的目的。不需要科学上网，也不需要海外的服务器辅助。

### 1\. 获取GitHub官方CDN地址

查询以下三个链接的DNS解析地址，记录下查询到的IP地址。

github.com

assets-cdn.github.com

github.global.ssl.fastly.net

### 2\. 修改系统Hosts文件

打开系统hosts文件(需管理员权限)。

路径：C:\\Windows\\System32\\drivers\\etc

在末尾添加三个链接的记录并保存。(需管理员权限，注意IP地址与域名间需留有空格)


记录可能有多个。

    1140.82.114.4 github.com
    185.199.108.153 assets-cdn.github.com
    185.199.109.153 assets-cdn.github.com
    185.199.110.153 assets-cdn.github.com
    185.199.111.153 assets-cdn.github.com
    199.232.69.194 github.global.ssl.fastly.net
    

### 3\. 刷新系统DNS缓存

Windows+X 打开系统命令行（管理员身份）或powershell

运行 ipconfig /flushdns 手动刷新系统DNS缓存。

现在打开Github，clone一个项目到本地试试吧，电信的宽带会轻松达到10M/s的速度。
