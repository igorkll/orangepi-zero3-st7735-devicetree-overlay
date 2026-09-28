# orangepi-zero3-st7735-devicetree-overlay
![preview](https://raw.githubusercontent.com/igorkll/orangepi-zero3-st7735-devicetree-overlay/refs/heads/main/images/orangepi_zero3_st7735_connection.png)  
device tree overlays and st7735 screen connection diagram for orange pi zero 3  
this method will also allow you to use the GPU renderer on your display.  
unlike management via userspace or fbtft  
enable "CONFIG_DRM_ST7735R=m" or "CONFIG_TINYDRM_ST7735R=m" in the kernel config to use (depends on the kernel version)  

## overlays
* display_128x160.dtso - describes the connections of the display itself (160x128)
* display_128x128.dtso - describes the connections of the display itself (128x128)
* disable_hdmi.dtso - disables the board's built-in HDMI port so that all applications and plymouth automatically use the display

## display connection
* V3.3 - VCC (Power)
* GND - GND (Groud)
* PH9 - CS (Chip select)
* PC11 - RESET
* PC6 - A0/DC (Data/Command)
* PH7 - SDA (MOSI)
* PH6 - SCK (CLK/Clock)
* PC15 - LED (Backlight)

## commands
* compile dtbo from dtso: dtc -I dts -O dtb -o display.dtbo -@ display.dtso

## add overlay
* armbian: sudo armbian-add-overlay display_128x160.dts (the repository contains files with the dtso and dtbo extensions. but you probably need to take the dtso and rename it to dts in order for utilities to accept it)

## you may also be interested in the following projects
* https://github.com/igorkll/syslbuild
* https://github.com/igorkll/panel-mipi-dbi-firmwares-and-overlays
