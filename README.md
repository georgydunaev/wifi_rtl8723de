# wifi_rtl8723de
Solution for case if rtl8723de doesn't work or works but has weak signal.

at first download an unpack from one of this places: 
https://github.com/jeremyb31/rtl8723de
https://github.com/georgydunaev/rtl8723de
https://github.com/smlinux/rtl8723de

sudo dkms add ./rtl8723de
fix osdep_service_linux.h as it told in wifi.txt
add this to Makefile in 
/usr/src/
OR in 
sudo gedit /var/lib/dkms/rtl8723de/5.1.1.8_21285.20171026_COEX20170111-1414/source/Makefile 
(if you already done: )

EXTRA_CFLAGS += -Wno-date-time
EXTRA_CFLAGS += -Wno-incompatible-pointer-types

Then:
sudo dkms install rtl8723de/5.1.1.8_21285.20171026_COEX20170111-1414

Then reboot.
