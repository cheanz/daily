# run tests on SBC zero

## 注意事项
* 保证SD卡inserted 天线接紧 TTL颜色顺序黑白绿 以及黑线对应黑pin
# Ubuntu 22.04 采用最新的Debian上游 默认内置brltty 这个package will occupy ttyUSB0  
solved:  
```
sudo apt purge brltty
sudo apt autoclean &&  sudo apt autoremove
```
## disable overlayroot  
进入chroot  
```
apt uninstall overlayroot 
```
## chmod -x filename  
r-- 100 4
-w-  10 2
--x   1 1
rwx 111 7
