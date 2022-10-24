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


## 看版本
https://linux.cn/article-9586-1.html  
详见以上网址，好用的是way 1  

**Way 1**  
lsb_release -a  

**Way 2** 

uname -r 或 cat /proc/version  

## 防火墙
启动： systemctl start firewalld  
查看状态： systemctl status firewalld   
禁用，禁止开机启动： systemctl disable firewalld  
停止运行： systemctl stop firewalld  
https://www.cnblogs.com/leoxuan/p/8275343.html#:~:text=CentOS7%20%EE%80%80%E9%98%B2%E7%81%AB%E5%A2%99%EE%80%81%EF%BC%88%EE%80%80firewall%EE%80%81%EF%BC%89%E7%9A%84%E6%93%8D%E4%BD%9C%EE%80%80%E5%91%BD%E4%BB%A4%EE%80%81%20%E5%AE%89%E8%A3%85%EF%BC%9Ayum%20install%20firewalld%201%E3%80%81firewalld%E7%9A%84%E5%9F%BA%E6%9C%AC%E4%BD%BF%E7%94%A8%20%E5%90%AF%E5%8A%A8%EF%BC%9A,systemctl%20start%20firewalld%20%E6%9F%A5%203.%E4%BF%A1%E4%BB%BB%E7%BA%A7%E5%88%AB%EF%BC%8C%E9%80%9A%E8%BF%87Zone%E7%9A%84%E5%80%BC%E6%8C%87%E5%AE%9A%20drop%3A%20%E4%B8%A2%E5%BC%83%E6%89%80%E6%9C%89%E8%BF%9B%E5%85%A5%E7%9A%84%E5%8C%85%EF%BC%8C%E8%80%8C%E4%B8%8D%E7%BB%99%E5%87%BA%E4%BB%BB%E4%BD%95%E5%93%8D%E5%BA%94  


## 音量
https://blog.csdn.net/weixin_43046653/article/details/105583100  
alsamixer，打开可视化，依次滚动鼠标滚轮，修改每一个的音量的上下，没有再F6选择声卡。

## 查找文件
用grep 方法：grep -n scaler ./  
find ./ -name st.cmd.acr
