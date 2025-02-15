## windows10家庭版 增加NFS服务  
### Windows 10 家庭版本身默认没有直接集成 NFS 服务，不过可以通过安装 “服务 for NFS” 功能来添加该服务。以下是详细步骤：  
1. 安装 “服务 for NFS”
	1. 启用 “适用于 Linux 的 Windows 子系统”（前提条件）：
		1. 打开 “Microsoft Store” 应用，搜索 “适用于 Linux 的 Windows 子系统” 并安装。
		1. 安装完成后，以管理员身份运行命令提示符，输入以下命令并回车，以启用 “适用于 Linux 的 Windows 子系统” 功能：
			`dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`	
	1. 安装 “服务 for NFS”：
		1. 按 “Win + R” 组合键打开 “运行” 对话框，输入 “OptionalFeatures” 并回车，打开 “Windows 功能” 窗口。
		1. 在 “Windows 功能” 窗口中，找到并展开 “服务 for NFS” 选项。
		1. 勾选 “NFS 客户端” 选项，如果您还想将此计算机设置为 NFS 服务器，则同时勾选 “NFS 服务器” 选项 。
		1. 点击 “确定” 按钮，系统会自动下载并安装所需的组件。安装完成后，可能需要重启计算机使更改生效。
1. 配置 NFS 客户端  
安装完成后，就可以使用 NFS 客户端连接到 NFS 服务器了。
	1. 查找 NFS 服务器共享目录：
		- 以管理员身份打开命令提示符，使用以下命令查看 NFS 服务器上的共享目录，其中<NFS服务器IP地址>替换为实际的 NFS 服务器 IP：  
			`showmount -e <NFS服务器IP地址>`
	1. 创建本地挂载点：
		- 在本地磁盘上创建一个空文件夹，用于挂载 NFS 服务器上的共享目录。例如，在 C 盘根目录下创建一个名为 “NFSMount” 的文件夹。
	3. 挂载 NFS 共享目录：
		- 使用以下命令将 NFS 服务器上的共享目录挂载到本地创建的挂载点，其中<NFS服务器IP地址>是 NFS 服务器的 IP，<共享目录名>是 NFS 服务器上的共享目录名称，<本地挂载点>是本地创建的挂载点路径：  
			`mount <NFS服务器IP地址>:/<共享目录名> <本地挂载点>`    
			`例如：mount 192.168.1.100:/shared /c/NFSMount`
1. 配置 NFS 服务器（可选）  
如果您想将 Windows 10 家庭版计算机配置为 NFS 服务器，向其他设备提供共享服务：
	1. 创建共享文件夹：在本地磁盘上创建一个文件夹，作为要共享的 NFS 目录。
	1. 设置共享权限：
		- 右键点击共享文件夹，选择 “属性”。
		- 在 “共享” 选项卡中，点击 “共享” 按钮，设置共享用户和权限。
	1. 配置 NFS 服务器：
		- 打开 “服务器管理器”（可通过开始菜单搜索）。
		- 依次点击 “文件和存储服务” - “共享”，在右侧点击 “新建共享”。
		- 按照向导提示，选择 NFS 共享类型（如 “NFS 共享 - 快速” 或 “NFS 共享 - 高级”），并设置共享路径、权限等参数。
		- 完成设置后，点击 “创建” 完成 NFS 服务器的配置。
