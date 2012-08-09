Author: Godmachine81 <Lance Poore linuxsociety@gmail.com>

Acer Iconia A100 Kernel Sources for Jelly Bean <Android 4.1.x>

DISCLAIMER:

FIRST OF ALL THIS IS  NOT AN OFFICIAL KERNEL, IT IS NOT SUPPORTED BY OFFICIAL CM10 ROMS OR ANY PREVIEW ROMS.
ONCE YOU INSTALL THIS KERNEL YOU WILL NOT BE SUPPORTED IN THE CM10 / CM9 OFFICIAL/UNOFFICIAL DEVELOPMENT THREADS
OF ANY FORUM i.e XDA, SLATEDROID, etc.. THIS MEANS THAT YOU MUST NOT REPORT ANY ANDROID / CM BUGS TO THE ORIGINAL
COMMUNTIY THREADS FOR THE ROM YOU USE! YOU MAY HOWEVER REPORT ANY CM/ANDROID/KERNEL RELATED ISSUES TO THE FOLLOWING
THREAD ON XDA:  http://forum.xda-developers.com/showthread.php?p=29876708

What's included:

*Overclocking up to 1500mhz (default is stock 1000mhz)
*I/O Schedulers: BFQ, CFQ, SIO, DEADLINE, NOOP
*Default configuration is set to use SCHED_AUTOGROUP to increase performance over the old CFS default scheduler
*CPU Governors: Lulzactive, Interactive, Ondemand, Powersave, Userspace, Performance (default interactive)
*Alsa SoC Tiny HAL patch for better compatibility with Jelly Bean (reduces/eliminates popping sounds)

What doesn't work:
*Attempted to patch sources for use with BFS v404-421 with instability at both stock clocking and overclockings (removed possibly permanently!)
*V(R) I/O scheduler fails to compile currently - will work on fixing errors or will remove it from the source tree. 

Configurtion:
Recommended config is in arch/arm/configs/vangogh_defconfig (includes all of the above additions)

Prebuilts:
Check the downloads section - .zip is flashable with TWRP/CWM in recovery mode

