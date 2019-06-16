<u>**8822BU for Linux**</u>

Driver for 802.11ac USB Adapter with  
RTL8812BU or RTL8822BU Chipset
Only STA/Monitor Mode is supported, no AP.  

To enter Monitor Mode:
airmon-ng check-kill
ip link set <interface> down
iw dev <interface> set type monitor

> NOTE: At least v4.7 is needed to compile this module
> sorry people with older kernels, the code is removed.
> Upon request I can work towards making it backwards compatible.

Currently tested on X86_64 and ARM platform(s) **only**,  
cross compile possible.

Included Cross Compile option for ARM64.

For compiling type  
`make`  
in source dir  

To install the firmware files  
`sudo make install`

To Unload driver you may need to disconnect the device or just reboot.

If the driver fails building consult your distro how to  
install the kernel sources and build an <u>external</u> module.


**NOTES**  
This driver allows use of wpa_supplicant by using the nl80211 driver
`wpa_supplicant -Dnl80211`

If installing on Rasberry Pi or other "armv71" devices, edit the Makefile and set `CONFIG_PLATFORM_ARM_RPI = y` and `CONFIG_PLATFORM_I386_PC = n`

For armv8 devices, edit the Makefile and set `CONFIG_PLATFORM_ARM_RPI64 = y` and `CONFIG_PLATFORM_I386_PC = n` 

**STATUS**  
Driver works fine (some sort of)  
Most of the work is done is cleaning the driver and make this mess **readable**   for conversion.
Updates for wireless-ext/cfg80211  are not accepted.  

**BUGS**  
