The REMnux&trade; distribution includes many free tools useful for examining malicious software. These utilities are set up and tested to make it easier for you to perform malware analysis tasks without needing to figure out how to install them. The majority of these tools are listed below.

For more details, including each tool's description and source, see the XLSX [spreadsheet](https://REMnux.org/remnux-tools-sheet.xlsx) or the XMind-formatted [mind map](https://REMnux.org/remnux-tools-map.xmind). You can also get an overview of the key tools and commands on the [REMnux cheat sheet](https://zeltser.com/remnux-malware-analysis-tips/).

## Examine Browser Malware

- Website analysis: [Thug](https://github.com/buffer/thug), [mitmproxy](http://mitmproxy.org/), [Network Miner Free Edition](http://www.netresec.com/?page=NetworkMiner), [curl](http://curl.haxx.se/), [Wget](https://www.gnu.org/software/wget/), [Burp Proxy Free Edition](http://portswigger.net/burp/), [Automater](http://www.tekdefense.com/automater/), [pdnstool](https://github.com/chrislee35/passivedns-client),  [Tor](https://www.torproject.org/), [tcpextract](http://tcpxtract.sourceforge.net/), [tcpflow](https://github.com/simsong/tcpflow), passive.py, [CapTipper](https://github.com/omriher/CapTipper)
- Flash: [xxxswf](http://hooked-on-mnemonics.blogspot.com/2011/12/xxxswfpy.html), [SWF Tools](http://www.swftools.org/), [RABCDAsm](https://github.com/CyberShadow/RABCDAsm), [extract_swf](https://gist.github.com/noonat/821548), [Flare](http://www.nowrap.de/flare.html)
- Java: [Java Cache IDX Parser](https://github.com/Rurik/Java_IDX_Parser/), [JD-GUI Java Decompiler](http://jd.benow.ca/), [JAD Java Decompiler](http://varaneckas.com/jad), [Javassist](http://www.javassist.org), [CFR](http://www.benf.org/other/cfr/)
- JavaScript: [Rhino Debugger](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino/Debugger), [ExtractScripts](http://blog.didierstevens.com/programs/extractscripts/), [Firebug](http://getfirebug.com/),  [SpiderMonkey](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/SpiderMonkey), [V8](https://code.google.com/p/v8/), [JS Beautifier](https://github.com/einars/js-beautify)

## Examine Document Files

- PDF: [AnalyzePDF](https://github.com/hiddenillusion/AnalyzePDF), [Pdfobjflow](http://www.aldeid.com/wiki/Pdfobjflow), [pdfid](http://blog.didierstevens.com/programs/pdf-tools/), [pdf-parser](http://blog.didierstevens.com/programs/pdf-tools/), [peepdf](http://eternal-todo.com/tools/peepdf-pdf-analysis-tool#releases), [Origami](https://code.google.com/p/origami-pdf/), [PDF X-RAY Lite](https://github.com/9b/pdfxray_lite), [PDFtk](http://www.pdflabs.com/tools/pdftk-the-pdf-toolkit/), [swf_mastah](http://blog.9bplus.com/snatching-swf-from-pdfs-made-easier/)
- Microsoft Office: [officeparser](https://github.com/unixfreak0037/officeparser), [pyOLEScanner.py]( https://github.com/Evilcry/PythonScripts/raw/master/), [oletools](http://www.decalage.info/python/oletools), [libolecf](https://github.com/libyal/libolecf), [oledump](http://blog.didierstevens.com/programs/oledump-py/), [emldump](https://isc.sans.edu/diary/Malicious+Word+Document+This+Time+The+Maldoc+Is+A+MIME+File/19673/)
- Shellcode: [sctest](http://libemu.carnivore.it/), unicode2hex-escaped, unicode2raw, [dism-this](http://hooked-on-mnemonics.blogspot.com/2012/10/dism-thispy.html), [shellcode2exe](https://github.com/MarioVilas/shellcode_tools/blob/master/shellcode2exe.py)

## Extract and Decode Artifacts

- Deobfuscate: [unXOR](https://github.com/tomchop/unxor/), [XORStrings](http://blog.didierstevens.com/2013/04/15/new-tool-xorstrings/), [ex_pe_xor](http://hooked-on-mnemonics.blogspot.com/2014/04/expexorpy.html), [XORSearch](http://blog.didierstevens.com/programs/xorsearch/), [brutexor/iheartxor](http://hooked-on-mnemonics.blogspot.com/p/iheartxor.html), [xortool](https://github.com/hellman/xortool), [NoMoreXOR](https://github.com/hiddenillusion/NoMoreXOR), [XORBruteForcer](http://eternal-todo.com/category/bruteforce), [Balbuzard](https://bitbucket.org/decalage/balbuzard/wiki/Home)
- Extract strings: [strdeobj](http://totalhash.com/download/strdeob.pl.txt), [pestr](http://pev.sourceforge.net/), [strings](http://en.wikipedia.org/wiki/Strings_(Unix))
- Carving: [Foremost](http://foremost.sourceforge.net/), [Scalpel](http://www.forensicswiki.org/wiki/Scalpel), [bulk_extractor](http://www.forensicswiki.org/wiki/Bulk_extractor), [Hachoir](https://bitbucket.org/haypo/hachoir)

## Handle Network Interactions

- Sniffing: [Wireshark](http://www.wireshark.org/), [ngrep](http://ngrep.sourceforge.net/), [TCPDump](http://www.tcpdump.org/), [tcpick](http://tcpick.sourceforge.net/)
- Services: [FakeDNS](http://code.activestate.com/recipes/491264-mini-fake-dns-server/), [Nginx](http://nginx.org/), [fakeMail](http://sourceforge.net/projects/fakemail/), [Honeyd](http://www.honeyd.org/), [INetSim](http://www.inetsim.org/), [Inspire IRCd](http://www.inspircd.org/), [OpenSSH](http://www.openssh.com/), accept-all-ips
- Miscellaneous network: [prettyping.sh](https://bitbucket.org/denilsonsa/small_scripts/src/3ec16014c839ea0852fae492813ad2293bd61155/prettyping.sh), set-static-ip, renew-dhcp, [Netcat](http://netcat.sourceforge.net/), [EPIC IRC Client](http://www.epicsol.org/), [stunnel](https://www.stunnel.org/)

## Process Multiple Samples

- [Maltrieve](https://github.com/technoskald/maltrieve), [Ragpicker](https://code.google.com/p/malware-crawler/), [Viper](https://github.com/botherder/viper), [MASTIFF](https://git.korelogic.com/mastiff.git/), [Density Scout](http://www.cert.at/downloads/software/densityscout_en.html)

## Examine File Properties and Contents

- Define signatures: [YaraGenerator](https://github.com/Xen0ph0n/YaraGenerator), [IOCextractor](https://github.com/stephenbrannon/IOCextractor), [Autorule](http://joxeankoret.com/blog/2012/04/29/extracting-binary-patterns-in-malware-sets-and-generating-yara-rules/), [Rule Editor](https://github.com/ifontarensky/RuleEditor)
- Scan: [Yara](http://plusvic.github.io/yara/), [ClamAV](http://www.clamav.net/), [TrID](http://mark0.net/soft-trid-e.html), [ExifTool](http://www.sno.phy.queensu.ca/~phil/exiftool/), [virustotal-submit](http://blog.didierstevens.com/programs/virustotal-tools/), [Disitool](http://blog.didierstevens.com/programs/disitool/)
- Hashes: [nsrllookup](https://github.com/rjhansen/nsrllookup), [Automater](http://www.tekdefense.com/automater/), [Hash Identifier](https://code.google.com/p/hash-identifier/), [totalhash](https://gist.github.com/malc0de/10270150), [ssdeep](http://ssdeep.sourceforge.net/), [virustotal-search](http://blog.didierstevens.com/programs/virustotal-tools/), [VirusTotalApi](https://github.com/doomedraven/VirusTotalApi)

## Investigate Linux Malware

- System: [Sysdig](http://www.sysdig.org/), [Unhide](http://www.unhide-forensics.info/)
- Disassemble: [Vivisect](http://visi.kenshoto.com/viki/Vivisect), [Udis86](http://udis86.sourceforge.net/), [objdump](http://en.wikipedia.org/wiki/Objdump)
- Debug: [Evan's Debugger (EDB)](http://codef00.com/projects#debugger), [GNU Project Debugger (GDB)](http://www.sourceware.org/gdb/)
- Trace: [strace](https://sourceforge.net/projects/strace/), [ltrace](http://ltrace.org/)
- Investigate: [Radare 2](https://github.com/radare/radare2), [Pyew](https://code.google.com/p/pyew/), [Bokken](https://inguma.eu/projects/bokken), [m2elf](https://github.com/XlogicX/m2elf)

## Edit and View Files

- Text: [SciTE](http://www.scintilla.org/SciTE.html), [Geany](http://www.geany.org/), [Vim](http://www.vim.org/)
- Images: [feh](http://feh.finalrewind.org/), [ImageMagick](http://www.imagemagick.org/)
- Binary: [wxHexEditor](http://sourceforge.net/projects/wxhexeditor/), [VBinDiff](http://www.cjmweb.net/vbindiff/)
- Documents: [Xpdf](http://www.foolabs.com/xpdf/)

## Examine Memory Snapshots

- [Volatility Framework](https://github.com/volatilityfoundation/volatility), [findaes](http://jessekornblum.livejournal.com/269749.html), AESKeyFinder, RSAKeyFinder, [VolDiff](https://github.com/aim4r/VolDiff), [Rekall](http://www.rekall-forensic.com/)

## Statically Examine PE Files

- Unpacking: [UPX](http://upx.sourceforge.net/), [Bytehist](https://www.cert.at/downloads/software/bytehist_en.html), [Density Scout](http://www.cert.at/downloads/software/densityscout_en.html), [PackerID](http://handlers.sans.org/jclausing/packerid.py)
- Disassemble: [objdump](http://en.wikipedia.org/wiki/Objdump), [Udis86](http://udis86.sourceforge.net/), [Vivisect](http://visi.kenshoto.com/viki/Vivisect)
- Find anomalies: [Signsrch](http://aluigi.altervista.org/mytoolz.htm), [pescanner](https://code.google.com/p/malwarecookbook/source/browse/trunk/3/8/pescanner.py), [ExeScan](http://securityxploded.com/exe-scan.php), [pev](http://pev.sourceforge.net/), [Peframe](https://github.com/guelfoweb/peframe), [pedump](http://pedump.me/)
- Investigate: [Bokken](https://inguma.eu/projects/bokken), [RATDecoders](https://github.com/kevthehermit/RATDecoders), [Pyew](https://code.google.com/p/pyew/), [readpe.py](https://github.com/crackinglandia/pype32), [PyInstaller Extractor](https://github.com/zrax/pycdc)

## Investigate Mobile Malware

- [Androwarn](https://github.com/maaaaz/androwarn), [AndroGuard](https://github.com/androguard/androguard)

## Perform Other Tasks

- [ProcDOT](http://www.procdot.com/), [bashhacks](https://github.com/merces/bashacks), [Docker](http://www.docker.com/), [vtTool](https://code.google.com/p/malware-crawler/wiki/vtTool), REMnux Updater, [Decompyle++](https://github.com/zrax/pycdc)

## Install Additional Tools

- [Metasploit](https://github.com/rapid7/metasploit-framework) is not installed on REMnux; however, [you can install it yourself](https://zeltser.com/install-metasploit-on-remnux/) if the need arises.

- [WIPSTER](https://github.com/TheDr1ver/WIPSTER) offers a web-based interface to several REMnux tools. You can easily install WIPSTER on REMnux by running the command `install-wipster`.
