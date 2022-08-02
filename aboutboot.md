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
* control pass to reset vector(the manufacture preprogram on to the board
* ROM Bootloader: setup basic hardware and find first stage bootloader from a boot device(network, memory bus
usb, sd card),load first stage bootloader into SoC internal memory and pass control to it.
* first stage bootloader: fetch second stage bootloader into RAM
* second stage :load the kernel and device tree into RAM; read its configurationi settings(statically embedded or external file); set up the Kernel Boot Arguments; Pass control to Kernel which uises the Boot Args and Device tree address to initializes itself and hardeare devices.
***
kernel: using Boot Arfs, Kernel locates and mounts the root filesytem; run init process(PID 0) to start userspace ; 
## distinguish between "pass control" and "call"  
pass control means: the previous program cease to exist
call means： the following process will return to the previous process
***
AMD integrate memory controller into cpu which is used to be external north bridge.
