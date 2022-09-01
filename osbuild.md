planning:
1. figure out the procedure to build an os
2. know how many tools and distinguiosh among them
3. realize an os for zero
## verbal
in a vat of molasses 在一大桶糖浆里  
SUSE linux操作系统  
Gentoo linux操作系统  
arch linux  
GNU GNU is not unix 一种类unix操作系统
congruence 一致；合适；全等  
full fledged: 经过充分训练的
qemu:   
breach: 破坏
## knowledge
package manager： source packages vs. binary packages.   
tarball： 原始码；linux下最方便的打包工具。  
encrypting:  
decrypting:  
virtualization: os together with application. A physical server running three virtual machines would have a hypervisor and three separate operating systems running on top of it.  
container:  Put simply, a container consists of an entire runtime environment: an application, plus all its dependencies, libraries and other binaries, and configuration files needed to run it, bundled into one package.   By containerizing the application platform and its dependencies, differences in OS distributions and underlying infrastructure are abstracted away.  
openssl: OpenSSL是一个开放源代码的软件库包，应用程序可以使用这个包来进行安全通信，避免窃听，同时确认另一端连线者的身份。这个包广泛被应用在互联网的网页服务器上。 其主要库是以C语言所写成，实现了基本的加密功能，实现了SSL与TLS协议
socket:
TCP:

# procedure
sudo apt-get -y install libslirp-helper
docker engine：

# about rootfs
inode
memory resident
Copy (archive files) in and out (of an archive)
ramdisk
cpio: backup format
# check concrete content of inode  
1. `stat`

# 尝试利用debos-radxa  
![Screenshot from 2022-09-01 14-45-59](https://user-images.githubusercontent.com/59786755/187849799-24e92fe4-bfc2-4893-89a0-2341abe59589.png)
![Screenshot from 2022-09-01 14-47-29](https://user-images.githubusercontent.com/59786755/187849838-f20b0c1c-8bc1-4473-8bf8-3f5d06e6c892.png)

