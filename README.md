# CQ-IOE
Beaglebone Black IO expansion for codesys

Chong Qi Electric Co. 創琦電機有限公司
TEL: 07-3743323

Type :  CQ-IOE

# PCB
Dimension: 232mm x 78mm 

![image](https://github.com/chilung1224/CQ-IOE/blob/main/PCB_2D.jpg)

![image](https://github.com/chilung1224/CQ-IOE/blob/main/PCB_3D.jpg)

# interface:
24v Input x 1

Digital Output x 24

Digital Input x 24

RS485 x 1

Canbus x 1

Usb 5v type A x 1

# Schematic

[Schematic_CQ-IOE](https://github.com/chilung1224/CQ-IOE/blob/main/Schematic_CQ-IOE_2021-05-06.pdf)


# io mapping:
  部分pin需移除LCD support才能使用
  
[IO mapping](https://github.com/chilung1224/CQ-IOE/blob/main/IO%20mapping.pdf)

[codesys io setting](https://github.com/chilung1224/CQ-IOE/blob/main/GPIOs_P9_P8.csv)

# io config:
sudo nano TIIO-00A0.dts

dtc -O dtb -o TIIO-00A0.dtbo -b 0 -@ TIIO-00A0.dts

sudo cp TIIO-00A0.dtbo /lib/firmware/

sudo nano /boot/uEnv.txt

###Additional custom capes

uboot_overlay_addr4=/lib/firmware/TIIO-00A0.dtbo

#uboot_overlay_addr5=/lib/firmware/<file5>.dtbo

#uboot_overlay_addr6=/lib/firmware/<file6>.dtbo

#uboot_overlay_addr7=/lib/firmware/<file7>.dtbo

[TIIO-00A0](https://github.com/chilung1224/CQ-IOE/blob/main/TIIO-00A0.dts)


# How to remove LCD support:
go to /boot/uEnv.txt

modify blow line

###Disable auto loading of virtual capes (emmc/video/wireless/adc)

#disable_uboot_overlay_emmc=1

disable_uboot_overlay_video=1

#disable_uboot_overlay_audio=1

#disable_uboot_overlay_wireless=1

#disable_uboot_overlay_adc=1

# Reference:
https://github.com/beagleboard/capes/tree/master/beaglebone/Comms

http://www.ofitselfso.com/BeagleNotes/BeagleboneBlackPinMuxModes.php

https://learn.adafruit.com/introduction-to-the-beaglebone-black-device-tree/compiling-an-overlay

