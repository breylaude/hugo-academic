---
title: Installing Linux on an external HDD
date: 2023-03-25T01:46:03.079Z
draft: false
featured: false
tags:
  - Linux
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
I wanted to install Linux on a portable SSD I had and make it bootable from my laptop, so it needed UEFI support. I didn't find a nice method of doing it online, so I found my own way.

Before going over the instructions, I'll touch base on the difference between BIOS, EFI and UEFI. These are all methods of booting an operating system. BIOS is the legacy boot mode found on older computers. Newer computers, such as my Macbook, uses UEFI (which is the successor to EFI) which requires some more steps than BIOS when installing the OS.

To make a UEFI Linux install bootable, the drive must have a EFI boot partition, which is a FAT32 formatted partition that is at least 200MB big. To do a UEFI install, the install disk must also be in UEFI mode (if its not, it will not install a UEFI version of Linux).

# [](https://github.com/ignaslaude/starter-hugo-academic/blob/main/content/post/installing-linux-on-an-external-hdd/index.md#approach)Approach

Most methods I found online involved booting the system via the Live CD and installing the operating system unto the connected external HDD. However what I found is this will overwrite the bootloader on the computer's internal drive, thus after the install the drive must be repaired to make the machine bootable again.

My solution is to create a virtual machine (using VirtualBox) to boot the Linux Live CD from and install the OS and install the operating system onto the external HDD within the VM. This approach won't affect the internal drive in any way (as the VM is completely sandboxed) and should work with most Linux operating systems.

# [](https://github.com/ignaslaude/starter-hugo-academic/blob/main/content/post/installing-linux-on-an-external-hdd/index.md#steps)Steps

1. Install [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
2. Install [Oracle VM VirtualBox Extension Pack](https://www.virtualbox.org/wiki/Downloads). This is needed to connect USB2 and USB3 drives to the virtual machine.
3. If your host operating system is Linux, make sure your user is in the `vboxusers` group using `sudo usermod -aG vboxusers $USER`, make sure to reboot to refresh the groups
4. Download your Linux distribution of choice. Make sure its 64-bit for UEFI support
5. Create a new virtual machine in VirtualBox
6. Do **not** add a virtual hard disk, as we will be mounting the external HDD into the VM to act as the disk
7. Go into the VM settings and enable EFI support (Under System > Enable EFI)
8. Under USB, select the USB controller, try USB3.0 first and if it doesn't work try USB2.0
9. Boot up the virtual machine, when asked supply the ISO image to use
10. Mount the USB hard drive by click the USB icon at the bottom of the virtualbox window and selecting the USB drive (if you don't see the drive, try changing your USB controller in the options, see step 8)
11. Start the installer as normal
12. During disk partitioning, ensure you have at least 3 partitions:

* EFI Boot Partition (FAT32, at least 200MB)
* / (Root mountpoint, EXT4)
* Swap (Should be around the size of your computer's RAM capacity)

13. Install as normal
14. Shutdown the VM and the computer, try to boot the external HDD on the computer.

# [](https://github.com/ignaslaude/starter-hugo-academic/blob/main/content/post/installing-linux-on-an-external-hdd/index.md#results)Results

* Bootable system with UEFI support, that works on different computers
* Makes no changes to the computers internal HDD during installation
* Tested with Ubuntu