# Vigor2200x_route2DevelopBoard

vigor 2200x route change Development board

有线路由器 vigor 2200x 改成 开发板

路由器配置：

 cpu S3c4510B
 
 Start Address Setting
The start address of the System Manager special register area is initialized to 3FFFF91H. (You can also set the
start address to an arbitrary value by writing the address, 3FF0000H.) When you have set the start address of the
special register area, the register addresses are automatically defined as the start address plus the register’s
offset.
Assume for example, that a reset initialize the start address to 3FF0000H. The offset address of the ROMCON
register is 3014H. Therefore, the physical address for ROMCON is 3FF0000H + 3014h = 3FF3014H. If you then
modified the start address of the special register area to 3000000H, the new address for the ROMCON register
would be 3003014H.
 
 ram 4M sdram       k4s161622d  512K x 16Bit x 2 Banks Synchronous DRAM
 
 rom nor flash 1024k*8bit or 512k*16bit  E28F800

---------------------------

1. 引出串口
 > 电路改造已经完成。测试有效。（115200 8 1）

2. 引出jtag

https://blog.csdn.net/oXiaoXue123456789/article/details/79259847

https://www.elecfans.com/emb/arm/20110819210962_a.html

![image](https://user-images.githubusercontent.com/11971682/167244877-de86d0e7-4202-451e-932a-ba8aa8b93972.png)


3. 拆掉 rtl8019as 网卡芯片

-------
1. u-boot 替换
   > u-boot 2013.01 之后没有s3c4510相关内容了，所以暂定使用u-boot-2012.04
   
   > u-boot 2011.06 的boards.cfg 中有evb4510

2. rtems 移植
