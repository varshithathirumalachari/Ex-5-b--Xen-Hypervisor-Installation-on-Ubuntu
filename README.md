# Ex-5-b--Xen-Hypervisor-Installation-on-Ubuntu

## Aim:

To Install Xen Hypervisor (Para Virtualization) and Virtual Manager on Ubuntu 14.04.1

## Procedure:

1.	Install Ubuntu 14.04.1 and more importantly enable virtualization in boot options

2.	Open terminal and install xen hypervisor

sudo apt-get install xen-hypervisor-amd64

(Installing 64-bit hypervisor runs on 32 bit dom0 and also creates 64 bit domU) Then reboot (you don’t have to update grub)
sudo reboot

3.	After rebooting just to check if Xen booted with Linux

sudo xl info

sudo apt-get install bridge-utils

4.	Open /etc/network/interfaces and change it sudo gedit /etc/network/interfaces and type the following

auto lo
iface lo inet loopback

auto xenbr0
iface xenbr0 inet dhcp bridge_ports eth0

auto eth0
iface eth0 inet manual

Then restart network manager

sudo ifdown eth0 && sudo ifup xenbr0 && sudo ifup eth0

5.	Now install Virtual Machine Manager

sudo apt-get install virt-manager
 
Now restart your system.

6.	Open virtual machine manager and then start creating your virtual machines.

•	Click on create a new virtual machine icon.
•	Enter new VM name and select the process of installing OS.
(local media/network install/network boot/import existing disk image)
•	Locate your media for installing OS either through CD-ROM, or ISO image along with OS type and version.
•	Choose Memory and CPU settings by specifying RAM size and number of CPUs.
•	Enable the storage of the VM by specifying disk size.
•	Now the OS is ready to begin it’s installation process in your VM.
7.	Now the VM is ready with the specified OS installed within it.









## Result:
Thus, to Install Xen Hypervisor (Para Virtualization) and Virtual Manager on Ubuntu 14.04.1is successfully implemented.
