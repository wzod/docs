This section will contain documentation about the tools installed on the REMnux&trade; distro. Would you like to [contribute your insights on REMnux and its tools](../expand/contribute.md) to expand this document set?

## Tools Installed on REMnux

The [listing of tools installed on REMnux](tools.md) outlines and categorizes the utilities you can use for analyzing malicious software on REMnux. For additional details, take a look at the XLSX [spreadsheet](https://REMnux.org/remnux-tools-sheet.xlsx) or the XMind-formatted [mind map](https://REMnux.org/remnux-tools-map.xmind), which outline these tools.

## REMnux Cheat Sheet

The one-page [REMnux cheat sheet](https://zeltser.com/remnux-malware-analysis-tips/) highlights some of the most useful tools and commands available on REMnux. It's an especially nice starting point for people who are new to the distro.

## Recorded REMnux Webcasts

To get started with the REMnux distro and become familiar with some of its capabilities, tune into the following recorded webcasts:

- [Malware Analysis Essentials Using REMnux](https://www.sans.org/webcasts/malware-analysis-essentials-remnux-w-lenny-zeltser-98045) by Lenny Zeltser
- [What's New in REMnux v4](https://www.youtube.com/watch?v=4LzCr9qf5_Q) by Lenny Zeltser
- [How to analyze malware with REMnux's reverse-engineering malware tools](http://searchsecurity.techtarget.com/video/How-to-analyze-malware-with-REMnuxs-reverse-engineering-malware-tools) by Keith Barker

## Articles on Using REMnux

Here are some of the blog posts and articles written about using REMnux for malware analysis:

- [Dynamic Malware Analysis With REMnux](http://countuponsecurity.com/2015/01/13/dynamic-malware-analysis-with-remnux-v5-part-1/) by Luis Rocha, continued in [part 2](http://countuponsecurity.com/2015/01/21/dynamic-malware-analysis-with-remnux-v5-part-2/)
- [Memory Forensics With Volatility on REMnux](http://countuponsecurity.com/2015/03/16/memory-forensics-with-volatility-on-remnux-v5-part-1/) by Luis Rocha, continued in [part 2](http://countuponsecurity.com/2015/03/18/memory-forensics-with-volatility-on-remnux-v5-part-2/)
- [Getting What You Want Out of a PDF with REMnux](http://hiddenillusion.blogspot.com/2012/06/getting-what-you-want-out-of-pdf-with.html) by Glenn Edwards
- [REMnux: Reverse-Engineering Malware](http://www.techrepublic.com/blog/it-security/remnux-reverse-engineering-malware/) by Michael Kassner
- [Malware Analysis Lab - A Fast and Cost Effective "HowTo"](http://www.cybersquared.com/2012/06/malware-analysis-lab-a-fast-and-cost-effective-howto/) by ThreatConnect
- [REMnux Tutorial: Statically Analyse Portable Executablei (PE) Files](http://www.slideshare.net/RhydhamJoshi/remnux-tutorial1-statically-analyse-portable-executablepe-files) by Rhydham Joshi, continued in [Part 2: Extraction and Decoding of Artifacts](http://www.slideshare.net/RhydhamJoshi/remnux-tutorial2-extraction-and-decoding-of-artifacts)
- [Analyzing Office Weaponized Documents](https://dfir.it/blog/2015/06/17/analysts-handbook-analyzing-weaponized-documents/) by dfir it!
- [Malicious Documents - PDF Analysis in 5 Steps](http://countuponsecurity.com/2014/09/22/malicious-documents-pdf-analysis-in-5-steps/) by Luis Rocha
- [REMnux v6 for Malware Analysis: VolDiff](http://malwology.com/2015/06/25/remnux-v6-for-malware-analysis-part-1-voldiff/) by Anuj Soni

If you write or locate other tutorials or articles that demonstrate the use of REMnux, please [let Lenny Zeltser know](https://zeltser.com/contact/).

## Known Issues

When importing the REMnux virtual appliance into an old version of VMware Workstation, Fusion or Player, you may get the error message that states, "Failed to open virtual machine: Failed to query source for information." In this case, you should upgrade to a later version of VMware software. If upgrading is not feasible, you may be able to use the [VMware OVF Tool](https://www.vmware.com/support/developer/ovf/) to convert the REMnux OVA file to the VMX format.

When using VMware Fusion to run the REMnux virtual machine, the VM might stop recognizing the mouse clicks. [According to VMware](http://kb.vmware.com/selfservice/microsites/search.do?language=en_US&cmd=displayKC&externalId=2010041), this occurs when the "virtual machine detects the connected mouse as a USB device and not as a HID device. While the mouse pointer may still move within the virtual machine, mouse clicks do not register." To address the problem, edit the .VMX file of your REMnux virutal machine to include the following line:

    mouse.vusb.startConnected = "FALSE"

A handful of people running REMnux installation or update scripts within virtual machines noticed that the antivirus tool installed on their underlying host flagged some REMnux packages as malicious and blocked their download. This is a false alarm. However, if you encounter this, you might need to disable the host's anivirus tool while running the script or whitelist the offending files or URLs to avoid getting them blocked.
