---
title: How to experience CP/M-80 2.2 using MAME's Sharp X1 emulation?
date: 2022-03-27 12:00:00 +0530
categories: [CP/M, CP/M-80, CP/M-80 2.2]
tags: [cp/m, mame]
author: legacyinstaller
image:
  path: CPM-80-2.2-MAME-x1-5.webp
  width: 800   # in pixels
  height: 600   # in pixels
  alt: List of FIles in Sharp X1 CP/M-80 2.2
img_path: /assets/img/2022/March/27/
---

In the last tutorial, we saw [how to experience CP/M-80 2.2 using MAME's KAYPRO II emulation]({% post_url 2022-03-26-how-to-experience-cpm-80-22-using-mame-kaypro-ii-emulation %}){:target="_blank"}. There are three system on which we can run CP/M-80 2.2:

- KAYPRO II
- NCR Decision Mate V
- Sharp X1

In this tutorial, we are going to use the SHARP X1 emulation. You can download the files required for this tutorial from here:

- [CP/M-80 2.2 for Sharp X1 disk image files](https://archive.org/download/cpm-80-2.2-sharp-x-1/CPM-80%202.2%20%5BSharp%20X1%5D%20%285.25-DSDD%29.7z)
- [MAME Sharp X1 ROM](https://archive.org/download/mame-merged/mame-merged/x1.zip)
- [mame.ini file for Linux](/assets/Downloads/MAME/mame.ini.linux.tar.xz)
- [mame.ini file for Windows](/assets/Downloads/MAME/mame.ini.windows.zip)

## Installing CP/M-80 2.2

First you need to make sure you have installed MAME. For windows, see our tutorial on Legacy Installer on [how to install MAME on Windows](https://legacyinstaller.pcriot.com/vm-software/mame){:target="_blank"}. For linux, you can install mame from the official repository of your distribution. See [this page](https://pkgs.org/download/mame){:target="_blank"} for a list of distributions offering the package. If your distribution does not include mame in its repositories (highly unlikely), you can [build MAME from source](https://docs.mamedev.org/initialsetup/compilingmame.html){:target="_blank"}.

After you have installed MAME, you need to create a folder in which all the files related to the emulator will reside. Open a Terminal/Command Prompt window and move to that folder. Then run:

```terminal
$ mame -cc
```

You may need to specify the path to MAME if you are on Windows:

```console
> "C:\Program Files\MAME\mame.exe" -cc
```

This command will create some basic config files for MAME in that folder. Now open the folder in your File Manager and delete the `mame.ini`{: .filepath} file. Extract the `mame.ini`{: .filepath} file from the archive you downloaded above according to your platform and copy it to the folder in which you are storing all the files related to the emulator. Create a folder called `roms`{: .filepath} in that folder. Copy the ROMs archives to that folder. Do not extract the ROMs from the zip files. Move the zip files without extracting to the `roms`{: .filepath} folder.

Extract the disk image archive and copy the `Images/ImageDisk/disk01.imd`{: .filepath} file to that folder where you are storing all the files related to the emulator.

Now switch back to the terminal and run:

```terminal
$ mame x1
```

You need to prefix `mame` with the path on Windows as shown above. The MAME window should open like this:

![MAME's X1 emulation window](CPM-80-2.2-MAME-x1-1.webp)

If the window does not open and you get a ROM not found or similar error, see the [troubleshooting section](#troubleshooting) below. Press any key to continue. The emulation of this machine is not perfect. You will be informed about this by MAME. Press any key to continue. Wait until you get to this screen:

![Sharp X1 OS loader screen](CPM-80-2.2-MAME-x1-2.webp)

Press the CAPS LOCK key to enable UI control. Then press the TAB key to open the menu.

![Sharp X1 main menu](CPM-80-2.2-MAME-x1-3.webp)

Then click on `File Manager > floppydisk`. Choose the `disk01.imd`{: .filepath} file from the list and choose `Read-write`.

![Sharp X1 floppy disk image chooser](CPM-80-2.2-MAME-x1-4.webp)

Then click on `Return to Previous menu > Return to the machine`. Press the CAPS LOCK key once again to turn off UI control. Press `F` key and then `0` key to start CP/M-80 2.2. Enter the following command to install CP/M-80 2.2:

```terminal
A> movcpm
```
{: file='X1 (CZ-800C)[x1]-MAME 0.242 (LP64)'}

If the the command do not finish within 5 minutes, close you VM and start is again. Enter the `DIR` command to see a list of files. If it matches the screenshot below, then CP/M-80 2.2 is installed!

![List to files in Sharp X1 CP/M-80 2.2](CPM-80-2.2-MAME-x1-5.webp)

Now, you can close this window. The next time you open the emulator again, you don't need to go through all these steps. Just open your terminal and navigate to the folder where all the the files related to the emulator are stored and run:

```terminal
$ mame x1
```

You need to prefix the above command with the path to MAME on windows as shown above.

But this method is very troublesome and lengthy. We can make a shell script which runs the above command on linux:

```bash
#!/bin/bash
mame x1
```
{: file='CPM-80-x1.sh'}

and save the file as `CPM-80-x1.sh`{: .filepath}. Then make the script executable by running the following command in terminal after navigating to that folder:

```terminal
$ sudo chmod +x ./CPM-80-x1.sh
```

Then we can right click on that file and click on `Run as Program` to open the emulator. Some DEs and distros may have other methods of running shell scripts.

On Windows, it is much easier. Create a file called `CPM-80-x1.bat`{: .filepath} in that folder with the following contents:

```bash
"C:\Program Files\MAME\mame.exe" x1
```
{: file='CPM-80-x1.bat'}

Then double click on that file to launch the emulator.

That's it. We have installed and run CP/M-80 2.2 using the MAME's Sharp X1 emulation.

## Troubleshooting

First make sure that you have placed the roms files in the correct place. Do not extract the files. Place the zip files directly in the `roms` folder.

On Linux, there might be another error. MAME might have been configured to look in your `~/.mame`{: .filepath} folder for its config files. If that is the case, running the command `mame` without any parameters in the folder where you have stored the files would result in MAME opening in full screen instead of a window. If you are affected by this problem, here is the solution:

- Configure your file manager to show hidden files.
- Go to the `~/.mame`{: .filepath} folder.
- Delete the `mame.ini`{: .filepath} file there.
- Copy the `mame.ini`{: .filepath} file you downloaded from above to that folder.

The mame.ini file you downloaded above instructs MAME to look for another `mame.ini`{: .filepath} file in the current folder and use it if found. So, you can then follow the tutorial and everything will work.

### Some explanation

I asked you to replace the `mame.ini`{: .filepath} file with the one you downloaded from here. What are the differences between those files? Here are they:

- It instructs MAME to open in windowed mode instead of full screen.
- It modifies the key needed for enabling UI controls from Scroll Lock to Caps Lock. This is done because many keyboards do not have a Scroll Lock key.
- On Linux, it instructs MAME to first look for configuration files in the current directory, and if found, use them instead of the one from `~/.mame`{: .filepath} folder.

That is it.

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

- The [MAME emulator](https://mamedev.org/){:target="_blank"} is an open source project hosted on [github](https://github.com/mamedev/mame){:target="_blank"} developed by MAMEDev and contributors.
- The disk image used above was taken from [WinWorld](https://winworldpc.com/){:target="_blank"}.

