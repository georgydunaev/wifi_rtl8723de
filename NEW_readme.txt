https://askubuntu.com/questions/1086728/how-do-i-remove-rtl8723de-modules-using-dkms

sudo modprobe -r rtl8723de
sudo dkms remove rtl8723de/5.1.1.8_21285.20171026_COEX20170111-1414 --all
sudo depmod -a
Reboot and check:

sudo dkms status



user@hp:~$ man dkms
user@hp:~$ sudo dkms status
[sudo] password for user: 
rtl8723de, 5.1.1.8_21285.20171026_COEX20170111-1414, 4.19.0-10-amd64, x86_64: installed
rtl8723de, 5.1.1.8_21285.20171026_COEX20170111-1414, 4.19.0-9-amd64, x86_64: installed
wireguard, 0.0.20200215: added
user@hp:~$ man modprobe 
user@hp:~$ sudo dkms remove rtl8723de/5.1.1.8_21285.20171026_COEX20170111-1414 -k 4.19.0-10-amd64

-------- Uninstall Beginning --------
Module:  rtl8723de
Version: 5.1.1.8_21285.20171026_COEX20170111-1414
Kernel:  4.19.0-10-amd64 (x86_64)
-------------------------------------

Status: Before uninstall, this module version was ACTIVE on this kernel.

rtl8723de.ko:
 - Uninstallation
   - Deleting from: /lib/modules/4.19.0-10-amd64/updates/dkms/
 - Original module
   - No original module was found for this module on this kernel.
   - Use the dkms install command to reinstall any previous module version.

depmod...

DKMS: uninstall completed.
user@hp:~$ sudo dkms status
rtl8723de, 5.1.1.8_21285.20171026_COEX20170111-1414, 4.19.0-9-amd64, x86_64: installed
wireguard, 0.0.20200215: added
user@hp:~$ 


