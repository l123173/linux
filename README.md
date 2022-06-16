# linux

## 双屏幕显示
参考这个文章  
https://www.cnblogs.com/Jesuca/archive/2012/02/24/2366940.html  
主要有几个命令：
列出来有几个屏幕   xrandr --listmonitors  
列出来接口   xrandr | grep " connected " | awk '{ print$1 }'
找里面的conected    xrandr  

如果确实已经检测到2个显示器了，那就扩展一下就行了，如下命令：(你自己的左右就是左右方向)  
xrandr --output DisplayPort-1-3 --auto --left-of HDMI-1   
（具体参数参考下面的，HDM 是我正在显示的显示器，在他左边放了一个）  
[root@localhost X11]# xrandr
Screen 0: minimum 320 x 200, current 3840 x 1080, maximum 16384 x 16384  
**HDMI-1** connected primary 1920x1080+1920+0 (normal left inverted right x axis y axis) 527mm x 296mm  
   1920x1080     60.00*+  74.97    50.00    59.94    
   1920x1080i    60.00    50.00    59.94    
......  
......  
......  
**DisplayPort-1-3** connected 1920x1080+0+0 (normal left inverted right x axis y axis) 527mm x 296mm  
   1920x1080     60.00*+  
   1600x900      60.00    
