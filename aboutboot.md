# you have to mount the usb before you use it on linux.
how to mount it?
# /sys/dev and dev  
# virtual file system
# find real root dev  
```
cat /proc/cmdline # may be intermediate root filesystem
```
# dtname  

device tree
# cat?will delete file content?

# BOOT procedure linux embedded system
* SoC powered
* control pass to reset vector(the manufacture preprogram on to the board; reset vector is located at the very begining of EFL mode )
* ROM Bootloader: setup basic hardware and find first stage bootloader from a boot device(network, memory bus
usb, sd card),load first stage bootloader into SoC internal memory and pass control to it.
* first stage bootloader: fetch second stage bootloader into RAM  BIOS and UEFI not only load the operating system from a non-volatile device, they also initialize system hardware for operating system. Examples of first-stage bootloaders include BIOS, coreboot, Libreboot and Das U-Boot.

* second stage :load the kernel and device tree into RAM; read its configurationi settings(statically embedded or external file); set up the Kernel Boot Arguments; Pass control to Kernel which uises the Boot Args and Device tree address to initializes itself and hardeare devices.
***
BIOS: motherboard firmware. 1.CHECK ALL the device are placed well.2. search for a bootable device. then pass control to os. Limitations: 1.drive support using MBR which can only access < 2TB of the hard disk.
As a rsult UEFI occurs: Unified extensible firmware interface
kernel: using Boot Arfs, Kernel locates and mounts the root filesytem; run init process(PID 0) to start userspace ; 
SPL: secondary program loader. initialize DRAM and flash and usher u-boot.CONFIG_SPL_XXX
pc: BIOS ->MBR ->GRUB -> kernel
embeded system:Rom code –> SPL –> u-boot –> Linux kernel –> file system –> application
## distinguish between "pass control" and "call"  
pass control means: the previous program cease to exist
call means： the following process will return to the previous process
***
AMD integrate memory controller into cpu which is used to be external north bridge.
##  U-boot: secondstage bootloader (SSBL)
# packaging
DIP : dual in line
# Partition table
LBA defalt size: 512 bytes   
GPT disk : disk using GUID partition table  
MBR: master boot record . stored on the first zone on the disk; fixed size  
hard disk  
RAM: volatile: lose everything once power is removed.common type: Double data rate synchrounous dynamic random access memory: DDRSDRAM  
  DRAM: 1970s; Not regulated by clcok; asynchronous;  SDRAM,DDR SDRAM, ECC(error-correcting code) DRAM all belong to DRAM.
  SDRAM:sychronous; rely on clock to sychronize signals; transfer data on one edge of clock
  DDR: fetchdata both on leading edge and falling edge. From SDRAM to DDR SDRAM ...DDR2 SDRAM until DDR4 SDRAM, the operating voltage is lower while amount of data trasffered(words per clock cycle) is larger.
SSD: use flash memory  
SD card   
USB  
ddr memory  
ramdisk    
***
symbolic link: ln; = symlink

***
板级设备：开发板上的设备信息，例如 CPU数量，内存基地址，IIC接口上接了哪些设备，SPI上接了哪些设备。
.dtsi: 不同板子的通用文件。因为他们有共同的soc。类似于c语言中的头文件。所以dtsi描述的是SOC级信息
dts： 设备树；是一种文件； extension：.dts；描述板级信息
DTC： 工具； 用来将 DTS编译为二进制的DTB
