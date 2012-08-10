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
*I/O Schedulers: BFQ, CFQ, SIO, V(R), DEADLINE, NOOP
*Vangogh configuration is set to use SCHED_AUTOGROUP to increase performance over the old CFS default scheduler
*If you don't want autogroup, then you can use the "default" kernel which is explained below. 
*CPU Governors: Lulzactive, SmartassV2, Interactive, Ondemand, Powersave, Userspace, Performance (default interactive)
*Alsa SoC Tiny HAL patch for better compatibility with Jelly Bean (reduces/eliminates popping sounds)

What doesn't work:
?? - Fixed Zram and V(R) - 8-8-2012

Configuration (building from the tree yourself):
Recommended config is in config-autogroup (includes all of the above additions) with autogroup
The stock configuration is in config-default which is the exact same configuration minus CONFIG_SCHED_AUTOGROUP


Prebuilts:
Check the downloads section - .zip is flashable with TWRP/CWM in recovery mode
There are currently two different versions of the zip: default and autogroup - The differences are only 
Autogroup is enabled in the "autogroup" kernel, and the "default" kernel is built just like stock with the
addition of the above enhancements minus autogroup. 

Info on .zip updater script:
The .zip for this kernel does not modify your ramdisk/init files, it simply flashes a new zImage (kernel binary) 
to your device and replaces the wifi module with the new one for this kernel.  Other than the WiFi, this kernel
is built fully static, WiFi is built as a module so that Networking is brought up in userland and loaded with
userland settings, this helps give Android OS control over how your network interface loads firmware. 
Most of the .zip has been modified from ezTerry's last release as it was a great way to prevent damage to the boot
image and ramdisk - Thanks to ezTerry!

Project Sources:

Kernel.org - Mainline Linux Kernel - Thanks Linus Torvalds and Team!! 20+ yrs and counting of a great Kernel!!
Cyanogenmod/android_kernel_acer_t20-common - A100/A500 Cyanogenmod Sources - Bringing the best to your portable devices!
gokhanmoral/siyahkernel3 - Samsung Galaxy S2 - Thanks for sources of V(R) from 3.0 !!
ezterry/AcerTabKernel - A100/A500 - Great kernel during HC and ICS - Thanks for a GREAT kernel! - Basis of this project
http://www.cse.unsw.edu.au/~aaronc/iosched/ - Great sources for IO schedulers 
http://ck.kolivas.org/ - Con Kolivas - Very appreciated set of patches for mainline kernel
http://pf.natalenko.name/ - PF Kernel - A great mainline patch set including CK sources
... All other unmentioned sources, we greatly appreciate everything the same as above!!

Thanks to all who test and participate in bug testing with this kernel!! 
