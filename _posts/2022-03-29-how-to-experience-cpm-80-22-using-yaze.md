---
title: How to experience CP/M-80 2.2 using YAZE?
date: 2022-03-29 12:00:00 +0530
categories: [CP/M, CP/M-80, CP/M-80 2.2]
tags: [cp/m, other emulator]
author: legacyinstaller
image:
  path: CPM-80-2.2-YAZE-3.webp
  width: 786   # in pixels
  height: 533   # in pixels
  alt: List of Files in YAZE CP/M-80 2.2
img_path: /assets/img/2022/March/29/
---

In the tutorial [how to experience CP/M-80 2.2 using the Altair Z80 emulator]({% post_url 2022-03-25-how-to-experience-cpm-80-22 %}){:target="_blank"}, I said that there were three options to run CP/M-80 2.2. In this tutorial, we are going to use the third option: YAZE. You can download the files needed for this tutorial here:

- [YAZE sources for Linux](https://web.archive.org/web/20220329102455/https://www.mathematik.uni-ulm.de/users/ag/yaze-ag/devel/yaze-ag-2.51.3.tar.gz){:target="_blank"}
- [YAZE binaries for Windows](https://web.archive.org/web/20220329102257/https://www.mathematik.uni-ulm.de/users/ag/yaze-ag/winbinaries/index.html){:target="_blank"}

## Installing YAZE

### Linux

On Linux, you need to build YAZE from sources. Extract the source archive and delete the `Makefile`{: .filepath}. Rename the `Makefile_linux_your_architecture`{: .filepath} file to `Makefile`{: .filepath}. For example, I renamed `Makefile_linux_64_intel_nocona`{: .filepath} to `Makefile`{: .filepath} because I am on an Intel cpu. Then open a terminal and navigate to that folder. Run the following commands:

```terminal
$ make
$ sudo make install
```

Enter your password when asked. This will install YAZE on your system.

![sudo make install yaze](CPM-80-2.2-YAZE-1.webp)

You can now run yaze to start `YAZE`. Press any key when asked to do so. Read the imformation presented on your screen before pressing any key.

![YAZE running](CPM-80-2.2-YAZE-2.webp)

You will now get to the `A:` prompt. You can run the `DIR` command to see a list of files.

![List of Files on YAZE CP/M-80 2.2](CPM-80-2.2-YAZE-3.webp)

That's it for Linux. We have installed and used YAZE with CP/M-80 2.2.

### Windows

On Windows, double click the installer file to start installation of YAZE.

![YAZE Windows Installer](CPM-80-2.2-YAZE-4.webp)

Then click on Extract. It will install YAZE. You will see an icon on your Desktop called YAZE. Double click on it to start YAZE. Press any key when asked to do so. Read the imformation presented on your screen before pressing any key.

![YAZE on Windows](CPM-80-2.2-YAZE-5.webp)

That's it for Windows. We have installed and used YAZE with CP/M-80 2.2.

## Manuals

- [CP/M 2.0 Interface Guide](https://web.archive.org/web/20220221170434/http://www.cpm.z80.de/randyfiles/DRI/CPM_2_0_Interface_Guide.pdf){:target="_blank"}
- [CP/M 2.0 System Alteration Guide](https://web.archive.org/web/20220221170433/http://www.cpm.z80.de/randyfiles/DRI/CPM_2_0_System_Alteration_Guide.pdf){:target="_blank"}
- [CP/M 2.0 User's Guide for CP/M 1.4 Users](https://web.archive.org/web/20220324101601/http://www.cpm.z80.de/randyfiles/DRI/CPM_2_0_UG_for_CPM_1_4_Users.pdf){:target="_blank"}
- [CP/M User Manual](https://web.archive.org/web/20200215062937/http://www.cpm.z80.de/manuals/CPMUserMan.pdf){:target="_blank"}
- [CP/M 2.2 MANUAL](https://web.archive.org/web/20220121011443/http://www.cpm.z80.de/manuals/cpm22-m.pdf){:target="_blank"}
- [CP/M Reference Manual](https://web.archive.org/web/20220324101643/http://www.cpm.z80.de/manuals/SC-CPM.pdf){:target="_blank"}

## Related Pages

- [WinWorld Page](https://winworldpc.com/product/cp-m-80/22){:target="_blank"}
- [Wikipedia](https://en.wikipedia.org/wiki/CP/M){:target="_blank"}
- [The Unofficial CP/M Web site](http://www.cpm.z80.de/){:target="_blank"}
- [Gaby's Homepage for CP/M and Computer History](http://z80.de/ehome.htm){:target="_blank"}
- [Commercial CP/M Software (Retro Archive)](http://www.retroarchive.org/cpm){:target="_blank"}
- [A lots of other links](http://z80.de/ecpmlink.htm){:target="_blank"}

## Credits

The YAZE enulator is an open source project created by [Andreas Gerlich](https://www.mathematik.uni-ulm.de/users/ag){:target="_blank"}. You can visit its [website](https://www.mathematik.uni-ulm.de/users/ag/yaze-ag/){:target="_blank"} to know more.
