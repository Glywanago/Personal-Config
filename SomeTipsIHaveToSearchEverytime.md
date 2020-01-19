# Increase VirtualBox video memory size
VBoxManage modifyvm "Name of VM" --vram 256
# drm problem flip done timeout add video=SVIDEO-1:d
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash video=SVIDEO-1:d"
# cpu fifo pipe idk
This driver uses SNA as the default acceleration method. You can try
falling back to UXA if you run into trouble. To do so, save a file with
the following content as /etc/X11/xorg.conf.d/20-intel.conf :
  Section "Device"
    Identifier  "Intel Graphics"
    Driver      "intel"
    Option      "AccelMethod"  "uxa"
    !Option      "AccelMethod"  "sna"
  EndSection
