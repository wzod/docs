The heart of the [REMnux](https://REMnux.org/)&trade; project is the REMnux Linux distribution based on [Ubuntu](http://www.ubuntu.com/). This lightweight distro incorporates many tools for analyzing Windows and Linux malware, examining browser-based threats such as obfuscated JavaScript, exploring suspicious document files and taking apart other malicious artifacts. Investigators can also use the distro to intercept suspicious network traffic in an isolated lab when performing behavioral malware analysis.

## Download the REMnux Virtual Appliance

The simplest way to get the REMnux distro is to [download its virtual appliance OVA file] (http://sourceforge.net/projects/remnux/files/version6/remnux-6.0-ova-public.ova/download). The file is 1.98 GB in size; its SHA-256 hash is C26BE9831CA414F5A4D908D793E0B8934470B3887C48CFE82F86943236968AE6.

You'll need to install virtualization software such as [VMware Player](http://www.vmware.com/products/player/), [VMware Workstation](http://www.vmware.com/products/workstation/), [VMware Fusion](http://www.vmware.com/products/fusion/) and [VirtualBox](https://www.virtualbox.org/) prior to using the REMnux virtual appliance.

Once you've downloaded the REMnux OVA file, import it into your virtualization software, then start the virtual machine. It will automatically log you into the environment using the user named "remnux". The user's password is "malware"; you might need to specify it when performing privileged operations.

After booting into the virtual appliance, run the `update-remnux full` command on REMnux to update its software. This will allow you to benefit from any enhancements introduced after the virtual appliance has been packaged. Your system needs to have Internet access for this to work.

## Install REMnux on an Existing System

As an alternative to downloading the virtual appliance, you can run the REMnux installation script on an existing Ubuntu 14.04 64-bit system. This allows you to install REMnux on a physical host or a virtual machine. You can use this method to add REMnux software and settings to a brand new system or to the host you've been using for a while. [SIFT Workstation ](http://digital-forensics.sans.org/community/downloads) users can utilize this approach to combine SIFT and REMnux into a single system.

If you'd like to build a REMnux system from scratch, use the [Ubuntu 14.04 64-bit minimal ISO](http://archive.ubuntu.com/ubuntu/dists/trusty/main/installer-amd64/current/images/netboot/mini.iso) as the starting point. If building a virtual machine, allocate at least 1GB of RAM and 25GB disk (more recommended). When going through the Ubuntu installer, consider creating the user named "remnux" with the password "malware", though any credentials will work. For step-by-step instructions, see the [screenshots of the Ubuntu installation steps](https://plus.google.com/photos/+REMnuxOrg/albums/6156978999037787521?authkey=CP2Zs4P-tZWcmQE).

Once you've logged into the newly-built or existing system compatible with REMnux, run the following command to install the REMnux distro:

    wget --quiet -O - https://remnux.org/get-remnux.sh | sudo bash

This installation script will configure your system and download and install the necessary software without asking you any questions. It requires Internet access to accomplish this. The installer will run for approximately 45 minutes, depending on the strength of your system and the speed of your Internet connection.

## Connecting the REMnux Virtual Appliance to the Internet

The REMnux virtual appliance is initially configured to use the "NAT" mode, so it can connect to the Internet through the host on which it is running. This way, if your underlying host has Internet connectivity, REMnux should be able to access the Internet as well. You can isolate REMnux within your lab by configuring the virtual appliance to use a "host only" network. After switching networks, run the `renew-dhcp` command in REMnux to refresh its network settings.

Some of the REMnux tools are designed to run in an [isolated laboratory environment](https://zeltser.com/vmware-network-isolation-for-malware-analysis/), so you can perform behavioral analysis of malicious software running in the lab. In this case, configure REMnux use a virtual network without Internet connectivity. Other tools are designed to allow you to explore suspicious websites and interact with online resources; REMnux will need to be connected to an Internet-accessible network when performing these tasks.

## Installing Virtualization Tools on REMnux

When running REMnux on a VMware platform, it's usually a good idea to install VMware Tools within the virtual machine. This will allow the REMnux screen resolution to automatically adust to match your monitor's geometry. It will also provide some additional enhancements, such as the opportunity to share clipboard contents across your underlying host and the virtual machine.

When running REMnux on VMware Workstation, Player or ESX, the simplest way to install VMware Tools using the open VM tools package by running the following command on REMnux, assuming it's connected to the Internet:

    sudo apt-get install open-vm-tools-desktop
    
On VMware Fusion, the best approach is to install proprietary VMware Tools. To do this, activate the VMware Tools installation via Virtual Machine > Install VMware Tools, then run the command `install-vmware-tools` on REMnux. You can install VMware Tools this way on VMware Workstation and Player as well. For additional details, see the [VMware article on this topic](http://kb.vmware.com/kb/1022525).

Please note that if you wish to use the shared folders feature of VMware, you will need to install proprietary VMware Tools with several adjustments to compensate for a compatibility issue between VMware Tools and the Ubuntu-supplied Linux kernel. These steps are described in an [article devoted to this topic](http://askubuntu.com/questions/586221/vmhgfs-module-not-compilable-for-vmware-tools-9-9-0-fusion7-1-after-ubuntu-lin). A more practical option for transferring files in and out of REMnux might be to use SFTP through the installed SSH server (`sshd start`) instead of using shared folders.

If using VirtualBox, consider installing Guest Additions software by following the [instructions provided by VirtualBox](https://www.virtualbox.org/manual/ch04.html).

## Updating Your REMnux System

To update REMnux after connecting your system to the Internet, simply run the `update-remnux` command. This tool will update the software that comprises the REMnux distribution, which includes the applications installed from standard Ubuntu and the REMnux-specific repository. The updater will also installed any tools added to the distro after your last update.
