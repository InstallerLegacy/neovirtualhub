---
title: How to install WordStar 3.3 on CP/M-80 2.2?
date: 2022-03-30 12:00:00 +0530
categories: [CP/M, CP/M-80, CP/M-80 2.2]
tags: [application, wordstar]
author: legacyinstaller
image:
  path: CPM-80-2.2-WordStar-3.3.webp
  width: 786   # in pixels
  height: 533   # in pixels
  alt: WordStar 3.3 on CP/M-80 2.2 on Altair Z80 emulator
img_path: /assets/img/2022/March/30/
---

In the last few tutorials we saw how to experience CP/M-80 2.2. But what use an OS is without some applications? In this tutorial we will see how to use WordStar 3.3 on CP/M-80 2.2 on Altair Z80 emulator. You can download the files required for this tutorial from here:

- [WordStar 3.3 package for Altair Z80s CP/M-80 2.2](https://web.archive.org/web/20220330051710/https://schorn.ch/cpm/zip/ws33.zip){:target="_blank"}

## Installing WordStar 3.3

First, you need to install CP/M-80 2.2 using Altair Z80 emulator. If have not already done so, see our tutorial on [how to experience CP/M-80 2.2]({% post_url 2022-03-25-how-to-experience-cpm-80-22 %}){:target="_blank"}. After you have installed CP/M-80 2.2, unzip the WordStar 3.3 package you downloaded from above. There are two files in that archive:

- ws33
- ws33.dsk

Copy those two files to the folder where you stored the files for CP/M-80 2.2. Now you can open a terminal/Command Prompt and enter the following command to start CP/M-80 2.2 with WordStar 3.3 diskette loaded:

```terminal
$ ./altairz80l64 ws33
```

Now type `b:` and press enter to switch to B drive. Enter the following command to start WordStar 3.3:

```terminal
B> ws
```

![WordStar 3.3 running on CP/M-80 2.2 on Altair Z80 emulator](CPM-80-2.2-WordStar-3.3.webp)

You can press `X` to exit WordStar. Read the mannuals linked below to learn how to use WordStar.
We will now create shell/Batch scripts to start CP/M-80 2.2 with WordStar 3.3 diskette loaded in B drive.

### On Linux

Create a file called `ws33.sh`{: .filepath} in the folder where you stored everything related to the VM with the following contents:

```bash
#!/bin/bash
./altairz80l64 ws33
```
{: file='ws33.sh'}

Save and close the file and make it executable by using this command:

```terminal
$ chmod +x ./ws33.sh
```

You need to execute the above command in the folder where you created that script. Now you can right click on that file and click on Run as Program to open the emulator. Some DEs and distros may have other methods of running shell scripts.

### On Windows

On windows create a file called `ws33.bat`{: .filepath} in the folder where the emulator files are located with the following contents:

```bash
altairz80l64.exe ws33
```
{: file='ws33.bat'}

Save and close that file. Now you can double click the file to open the emulator with the WordStar 3.3 diskette loaded.

That's it. We use WordStar 3.3, a software released in 1983.

## Manuals

- [WordStar Installation Manual For Release 3.3](https://web.archive.org/web/20200727101155/http://bitsavers.org/pdf/microPro/Wordstar_3.3/Wordstar_3.3_Installation_Manual_1983.pdf){:target="_blank"}
- [WordStar Reference Manual For Release 3.3](https://web.archive.org/web/20210223080731/http://www.bitsavers.org/pdf/microPro/Wordstar_3.3/Wordstar_3.3_Reference_Manual_1983.pdf){:target="_blank"}
- [WordStar 3.3 Training Guide](https://web.archive.org/web/20200727101209/http://bitsavers.org/pdf/microPro/Wordstar_3.3/Wordstar_Training_Guide_2ed_Feb83.pdf){:target="_blank"}

## Related Pages

- [WinWorld Page](https://winworldpc.com/product/wordstar/330){:target="_blank"}
- [Wikipedia](https://en.wikipedia.org/wiki/WordStar){:target="_blank"}
- [WordStar Resource Site](https://www.wordstar.org/){:target="_blank"}
- [Retroarchive WordStar Collection](http://www.retroarchive.org/cpm/text/wordstar-collection.html){:target="_blank"}

## Credits

The emulator which is linked above was created by [Peter Schorn](mailto:peter.schorn@acm.org){:target="_blank"}. You can visit [his website](https://schorn.ch/altair.html){:target="_blank"} to download the original emulator and lots of other software.
