# Arm Plugs


I have been using the following ARM based Linux Plug Devices for a Long time. These devices are very stable when used with HDD. I have used both with USB and HDD. But the USB has gone through multiple crashes down the line. Here I am jotting down some of the Lessons learned so far.

### Dockstar
- Doesn't have a USB 3 Ports
- No SATA Slot

### Pogoplug V4 - Pink
- Use a good Pern Drive/SD Card for Booting
- Recommeded to use HDD for the rootfs

# Basic Concepts 
- rootfs - Determines the Primary Partition to boot the OS via UBoot
- Kernel : Linux Kernel which has the core definition of the OS
- Debian : The Linux Distro which adds the necessary flavour
- Kernel and Debian can be Updated separately.
- UBoot is a BootLoader for ARM Devices. I have used only the Kirkwood Marvell Devices of ARMV5
- UBoot 2017 released by Bodhi. Please see the references Site for more details


#### References :
- https://forum.doozan.com