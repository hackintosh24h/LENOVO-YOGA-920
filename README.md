# LENOVO-YOGA-920
YOGA920-Hackintosh-OPENCORE
The EFI/OPENCORE file FOR Hacintosh - Yoga 920 (i7/8550u/Graphics-UHD620-4k/Trackpad and TouchScreen - I2C)
MAC OS Version: Catalina 10.15.7 and BigSur 11.0.1

Thanks mrGin
What is working

    Intel Graphic UHD620
    PS2 Keyboard
    TouchPad and TouchScreen work
    Battery and cpu sensor
    USB: 2/3, type-a/type-c, hot/cold plug, HDMI
    thunderbolt3 hot plug
    SSD
    Camera
    Hibernation and wake up
    Wlan Replaced to DW1820a
    Bluetooth 4.0 replaced to DW1820a
    Airdrop/Handoff/Sidecar

What is not working

    WIFI and Bluetooth card change to bcm94350 (DW1820A)
    Fingerprint

SSDT
#Battery Path

#Brightness Keys Patch

into method label _Q38 replace_content
begin
Notify (PS2K, 0x0406)
end;
into method label _Q39 replace_content
begin
Notify (PS2K, 0x0405)
end;

#leep

sudo pmset -a hibernatemode 0
sudo rm /var/vm/sleepimage
sudo mkdir /var/vm/sleepimage
sudo pmset -a standby 0
sudo pmset -a autopoweroff 0
