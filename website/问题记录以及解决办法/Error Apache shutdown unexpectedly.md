#Error: Apache shutdown unexpectedly.  
经搜索得知，可能是80端口被占用  
cmd输入netstat -ano,可以查看80端口占用的程序pid  
一开始以为是pid为4的系统进程，但是我不敢kill
cmd输入netsh http show servicestate  
出来一个pid为2884的进程，搜索了一下，感觉是网络设备发现程序，也不敢kill。  
正当我一筹莫展之际，想起了好像把xampp/htdoc里面的网页全部删掉了，想放自己的网页。好在做了备份，将里面的文件还原之后，xampp就能运行了。  
但是报了另一个错  
Port 443 in use by "D:\Steam++_v3.0.0-rc.1_win_x64\modules\Accelerator\Steam++.Accelerator.exe" with PID 6760!
好嘛，steam++占用了80端口，关掉这个进程，Apache可算是正常运行了。