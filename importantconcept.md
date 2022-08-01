# Uboot
a boot loader originally designed for PowerPC
PowerPC是一种精简指令集的指令集架构 ISA，其基本的设计源自IBM的POWER架构。
POWER： performance optimized with enhanced RISC

SPL

## POWER VS X86
X86 history
intel designed 8086 released in 1978, headof x86 family -16 bit

AMD64=X86_64=X64
AMD VS INTEL
CCXs ON CCD with infinity fabric
high yield, high scalability and low cost
Intel: monolithic chip design
EMIBS
FOVEROS chips stacking
device tree
dts,dtbo,blob
***
# PCie 总线
背景知识
## 并行总线和串行总线
带宽：总线的数据传输能力
并行代表： IEEE并行 (早期设备）  
需要照顾数据的协同传输，所以频率不能做的很高（霰弹枪）
线宽，针脚多，接口大,
链路干扰  
？？为什么会有干扰
串行代表： USB 硬盘SATA,显卡PCie(串行总线做多链路传输，链路的数据之间没有关系相互独立，可以是不同步的，频率不同的）（现代的设备都是串行）  
频率可以做很高（机枪）
## ISA （并行总线 带宽：8MB/S）
上世纪80年代 IBM 联合 Intel 为了统一电脑硬件接口，为PC/AT电脑制定了一个标准  
弊端： 收到cpu外频率影响；只能支持6个外设；带宽低;不能即插即用，要手动分配资源；
要在指定的cpu上才能使用。
## 于是出现了 PCI 总线来代替 ISA(并行总线 132MB/S 32BIT 264MB/S 64BIT)
共享总线：不同设备抢带宽
；不支持热拔插；
## 于是出现了 PCIe
接口：插显卡，固态硬盘，网卡，转接口等。满足高带宽
通道： M.2接口形状，实际数据传输依赖于PCIe.雷电3接口 thunderbolt3 (intel and apple)
带宽分配：
带宽：按长度计算。X1,X2残血,X4满血,X8,X16
PCIe 1.0,2.0,3.0,4.0 每代都在翻倍
?? 南桥通讯
## 
# mask rom
# armlogic
