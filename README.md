# orangepi-zero3-st7735-devicetree-overlay
device tree overlays and st7735 screen connection diagram for orange pi zero 3  

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
