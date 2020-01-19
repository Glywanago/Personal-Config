# Increase VirtualBox video memory size
VBoxManage modifyvm "Name of VM" --vram 256
# drm problem flip done timeout add video=SVIDEO-1:d
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash video=SVIDEO-1:d"
