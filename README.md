# Linux-
Linux基础知识

1 开机流程



1.	 载入	BIOS	的硬件信息与进行自我测试,并依据设置取得第一个可开机的设备;
2.	 读取并执行第一个开机设备内	MBR	的	boot	Loader	(亦即是	grub2,	spfdisk	等程序);
3.	 依据	boot	loader	的设置载入	Kernel	,Kernel	会开始侦测硬件与载入驱动程序;
4.	 在硬件驱动成功后,Kernel	会主动调用	systemd	程序,并以	default.target	流程开机;
systemd	执行	sysinit.target	初始化系统及	basic.target	准备操作系统;
systemd	启动	multi-user.target	下的本机与服务器服务;
systemd	执行	multi-user.target	下的	/etc/rc.d/rc.local	文件;
systemd	执行	multi-user.target	下的	getty.target	及登陆服务;
systemd	执行	graphical	需要的服务

