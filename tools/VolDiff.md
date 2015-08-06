VolDiff is a Python script that leverages the [Volatility](https://github.com/volatilityfoundation) framework to identify malware threats on Windows memory images.

This tool can be used to run a collection of Volatility plugins against memory images captured before and after malware execution. It creates a report that highlights system changes based on memory (RAM) analysis. VolDiff can also be used against a single Windows memory image to automate Volatility plugin execution, and hunt for malicious patterns.

##Category

Examine Memory Snapshots

##Usage

    VolDiff.py [BASELINE_IMAGE] INFECTED_IMAGE PROFILE [OPTIONS]

Options:
   * `--help`            display this help and exit
   * `--version`          display version information and exit
   * `--dependencies`      display information about script dependencies and exit
   * `--malware-checks`    hunt and report suspicious anomalies (slow, recommended)
   * `--no-report`         do not create a report

The default VirusTotal API key is limited to 4 requests per minute. If you have a PrivateAPI key, modify _vt_api_key_.

##Example

    VolDiff.py base_win7.vmem infected_win7.vmem Win7SP1x86 --malware-checks

##References

* [Memory Analysis of DarkComet using VolDiff](https://github.com/aim4r/VolDiff/wiki/Memory-Analysis-of-DarkComet-using-VolDiff) by aim4r
* [REMnux v6 for Malware Analysis (Part 1): VolDiff](http://malwology.com/2015/06/25/remnux-v6-for-malware-analysis-part-1-voldiff/) by Anuj Soni
* [VolDiff for Memory Image Differential Analysis](https://isc.sans.edu/diary/VolDiff,+for+memory+image+differential+analysis/19651) by Russ McRee

##Author and Source

* [@aim4r](https://twitter.com/aim4r)
* [Source code repository](https://github.com/aim4r/VolDiff)

## Location on REMnux

VolDiff.py is a part of the remnux-script package and is located in the /opt/remnux-scripts directory.
