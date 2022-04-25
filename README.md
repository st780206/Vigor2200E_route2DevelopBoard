# Vigor2200x_route2DevelopBoard

vigor 2200x route change Development board

有线路由器 vigor 2200x 改成 开发板

路由器配置：

 cpu S3c4510B
 
 ram 4M sdram       k4s161622d  2M*2
 
 rom nor flash 1024k*8bit or 512k*16bit  E28F800

---------------------------

1. 引出串口
 > 电路改造已经完成。测试有效。（115200 8 1）

2. 引出jtag

3. 拆掉 rtl8019as 网卡芯片

-------
1. u-boot 替换
   > u-boot 2013.01 之后没有s3c4510相关内容了，所以暂定使用u-boot-2012.04
   
   > u-boot 2011.06 的boards.cfg 中有evb4510

2. rtems 移植
