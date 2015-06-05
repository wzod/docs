The heart of the [REMnux](https://REMnux.org/)&trade; project is the REMnux Linux distribution based on [Ubuntu](http://www.ubuntu.com/). This lightweight distro incorporates many tools for analyzing Windows and Linux malware, examining browser-based threats such as obfuscated JavaScript, exploring suspicious document files and taking apart other malicious artifacts. Investigators can also use the distro to intercept suspicious network traffic in an isolated lab when performing behavioral malware analysis.

## Download the REMnux Virtual Appliance

The simplest way to get the REMnux distro is to [download its virtual appliance OVA file] (http://sourceforge.net/projects/remnux/files/version6/remnux-6.0-ova-public.ova/download). The SHA-256 hash of the file is (TBD).

You'll need to install virtualization software such as [VMware Player](http://www.vmware.com/products/player/), [VMware Workstation](http://www.vmware.com/products/workstation/), [VMware Fusion](http://www.vmware.com/products/fusion/) and [VirtualBox](https://www.virtualbox.org/) prior to using the REMnux virtual appliance.

Once you've downloaded the REMnux OVA file, import it into your virtualization software, then start the virtual machine. It will automatically log you into the environment using the user named "remnux". The user's password is "malware"; you might need to specify it when performing privileged operations.

After booting into the virtual appliance, run the `update-remnux full` command on REMnux to update its software. This will allow you to benefit from any enhancements introduced after the virtual appliance has been packaged. Your system needs to have Internet access for this to work.

## Install REMnux on an Existing System

Another way to get REMnux is to run its installation script on an existing system running Ubuntu 14.04 64-bit. This allows you to install REMnux on a physical host or a virtual machine. You can use this method to add REMnux software and settings to a host you've been using for a while or to a brand new system. [SIFT Workstation ](http://digital-forensics.sans.org/community/downloads) users can utilize this approach to combine SIFT and REMnux into a single system.

If you'd like to build A REMnux system from scratch, use the [Ubuntu 14.04 64-bit minimal ISO](http://archive.ubuntu.com/ubuntu/dists/trusty/main/installer-amd64/current/images/netboot/mini.iso) as the starting point. When going through the Ubuntu installer, consider creating the user named "remnux" with the password "malware", though any credentials will work. If building a virtual machine, allocate at least 1GB of RAM and 25GB disk (more recommended).

Once you've loged into the newly-built or existing system compatible with REMnux, run this command to install the REMnux distro:

    wget --quiet -O - https://remnux.org/get-remnux.sh | sudo bash

This installation script will configure your system and download and install the necessary software without asking you any questions. It requires Internet access to accomplish this. The installer will run for approximately 45 minutes, depending on the strength of your system and the speed of your Internet connection.

## Connecting the REMnux Virtual Appliance to the Internet

The REMnux virtual appliance is initially configured to use the "NAT" mode, so it can connect to the Internet through the host on which it is running. This way, if your underlying host has Internet connectivity, REMnux should be able to access the Internet as well. You can isolate REMnux within your lab by configuring the virtual appliance to use a "host only" network. After switching networks, run the `renew-dhcp` command in REMnux to refresh its network settings.

Some of the REMnux tools are designed to run in an [isolated laboratory environment](https://zeltser.com/vmware-network-isolation-for-malware-analysis/), so you can perform behavioral analysis of malicious software running in the lab. In this case, configure REMnux use a virtual network without Internet connectivity. Other tools are designed to allow you to explore suspicious websites and interact with online resources; REMnux will need to be connected to an Internet-accessible network when performing these tasks.

## Updating Your REMnux System

To update REMnux after connecting your system to the Internet, simply run the `update-remnux` command. This tool will update the software that comprises the REMnux distribution, which includes the applications installed from standard Ubuntu and the REMnux-specific repository. The updater will also installed any tools added to the distro after your last update.
