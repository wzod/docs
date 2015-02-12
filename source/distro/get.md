The heart of the [REMnux](https://REMnux.org/)&trade; project is the REMnux Linux distribution based on [Ubuntu](http://www.ubuntu.com/). This lightweight distro incorporates many tools for analyzing Windows and Linux malware, examining browser-based threats such as obfuscated JavaScript, exploring suspicious document files and taking apart other malicious artifacts. Investigators can also use the distro to intercept suspicious network traffic in an isolated lab when performing behavioral malware analysis.

## Download the REMnux Distro

You can [download the REMnux distribution](https://sourceforge.net/downloads/remnux/version5/) as a virtual appliance archive and as an ISO image of a Live CD:

- OVF/OVA virtual appliance: [remnux-5.0-ovf-public.ova](http://sourceforge.net/projects/remnux/files/version5/remnux-5.0-ova-public.ova/download) for most virtualization tools, including VMware and VirtualBox (MD5 hash e5ab6981d1a4d5956b05ed525130d41f)
- VMware virtual appliance: [remnux-5.0-vm-public.zip](http://sourceforge.net/projects/remnux/files/version5/remnux-5.0-vm-public.zip/download) only for VMware virtualization softare and includes VMware Tools (MD5 hash 77ec0701661caceaa1a5eef90c0bacd1).
- ISO image of a Live CD: [remnux-5.0-live-cd.iso](http://sourceforge.net/projects/remnux/files/version5/remnux-5.0-live-cd.iso/download) for ephemeral malware analysis sessions (MD5 hash a06b2603a13fba97f50818c2ab12bbe6).

Prior to using the REMnux virtual appliance, you'll need to obtain virtualization software such as [VMware Player](http://www.vmware.com/products/player/), [VMware Workstation](http://www.vmware.com/products/workstation/), [VMware Fusion](http://www.vmware.com/products/fusion/overview.html) and [VirtualBox](https://www.virtualbox.org/).

For detailed instructions specific to the OVF/OVA version, see the article [Installing the REMnux Virtual Appliance for Malware Analysis](http://digital-forensics.sans.org/blog/2013/04/10/installing-remnux-virtual-appliance). If using the OVF/OVA virtual appliance with VMware, you can optionally [install VMware Tools in REMnux](https://zeltser.com/install-vmware-tools-on-remnux/).

If you encounter problems installing REMnux, please see the tips, issues, errata and workarounds outlined in [REMnux Version 5 Installation Notes](https://github.com/REMnux/distro/blob/v5/remnux5-installation-notes.md).

## REMnux Distro Releases

Version 6 of REMnux is in the works and will be available in early 2015. It will be based on 64-bit [Ubuntu 14.04 LTS](http://releases.ubuntu.com/14.04/).

The latest release of the REMnux distro is version 5. It came out in May 2014. This release added new tools to the distribution and updated those that have been present the prior version. For more details related to REMnux v5, see [its release announcement](https://zeltser.com/remnux-v5-release-for-malware-analysts/).

Version 4 of the REMnux distro [came out in April 2013](https://zeltser.com/version-4-release-of-remnux-linux-distro-for-malware/). For details regarding REMnux v4, and to see the overview of the tools added to the distro as part of this release, [tune into the recorded webcast on this topic](https://www.youtube.com/watch?v=4LzCr9qf5_Q).

## Connecting REMnux to the Internet

The REMnux virtual appliance is configured to use the "host-only" network, isolating the REMnux instance from the physical network. To connect REMnux to the network, for instance, to provide it with Internet access, change the settings of the virtual appliance to the appropriate network, such as "NAT" then issue the `renew-dhcp` command in REMnux.
