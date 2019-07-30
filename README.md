# Linux-
Linux基础知识

1 开机流程
(1)载入	BIOS	的硬件信息与进行自我测试,并依据设置取得第一个可开机的设备;

(2)读取并执行第一个开机设备内MBR的bootLoader(亦即是grub2,spfdisk	等程序);
(3)依据	boot loader的设置载入Kernel,Kernel	会开始侦测硬件与载入驱动程序;
(4)在硬件驱动成功后,Kernel会主动调用	systemd程序,并以default.target流程开机;
      systemd	执行	sysinit.target初始化系统及basic.target准备操作系统;
      systemd	启动	multi-user.target下的本机与服务器服务;
      systemd	执行	multi-user.target下的/etc/rc.d/rc.local文件;
      systemd	执行	multi-user.target	下的getty.target及登陆服务;
      systemd	执行	graphical需要的服务

