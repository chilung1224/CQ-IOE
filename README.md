# CQ-IOE
Beaglebone Black IO expansion

Chong Qi Electric Co. 創琦電機有限公司

Type :  CQ-IOE

# interface:

Digital Output x 24

Digital Input x 24

RS485 x 1

Canbus x 1

Usb 5v type A x 1

# Schematic

https://github.com/chilung1224/CQ-IOE/blob/main/Schematic_CQ-IOE_2021-05-06.pdf

# io mapping:
  部分pin需移除LCD support才能使用
  
https://github.com/chilung1224/CQ-IOE/blob/main/IO%20mapping.pdf

# how to remove LCD support:
go to /boot/uEnv.txt

modify blow line

###Disable auto loading of virtual capes (emmc/video/wireless/adc)

#disable_uboot_overlay_emmc=1

disable_uboot_overlay_video=1

#disable_uboot_overlay_audio=1

#disable_uboot_overlay_wireless=1

#disable_uboot_overlay_adc=1

