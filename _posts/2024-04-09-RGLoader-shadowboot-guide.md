---
layout: post
category: guides
---

## Table of contents:
- [Introduction](#introduction)
- [Requirements](#requirements)
- [Set up](#set-up)
- [Uninstallation](#uninstallation)
- [FAQ](#faq)

---

## [Introduction](#introduction)
RGLoader is a mod, which patches the system to remove many limitations like code signing requirement, media limitations, mainly allowing you to launch any xex file.

It allows loading of external plugins, for example, stealth servers.

This is a completely safe and fully reversible modification because it does not involve any modifications to internal flash, and pretty much is the same like using Phoenix Bios Loader on OG Xbox or emunand on Nintendo Switch.

## [Requirements](#requirements)
- Xbox 360 __development__ kit. Fat test kits __WILL NOT__ work because they require a completely different method. Slim testkits, which have sidecar port, will work.
- [Main RGLoader files](https://drive.google.com/file/d/1X7D3hGnJv8U1Z84jiJoQ305kUzKN83Vf/view?usp=drive_link)
* A way to copy files over to XDK - neighborhood is recommended. You may follow a guide I mention [here](https://dzastsed.github.io/how-to-dump-your-xdk-nand-preservation-of-undumped-recoveries.html#preparations).

Optional but recommended:

* [System extended and auxilliary files](https://drive.google.com/file/d/1S7tSdoSLamsUWr8fzpa4FwjJVk9Dp01_/view?usp=sharing)
* A way of recovery if something goes wrong - recovery disc works, but ideal thing would be KDNet set up, you can use [this guide](https://byrom.uk/tuts/setupkdnet/) made by Byrom for that.

## [Set up](#set-up)

Simply extract downloaded `Main RGLoader files` and copy them over to HDD root.

After copying them over, restart the console.

### Optional: System extended/auxilliary files

TODO: Sysaux/ext guide

If anything went well, you should be greeted by RGLoader screen, congratulations!

If not, don't worry, and check [frequently asked questions](#faq).


## [Uninstallation](#uninstallation)

If you no longer want to use RGLoader, rename or delete xboxromw2d.bin on HDD root reboot your XDK. Also delete filesystems folder.


## [FAQ](#faq)

> Why does OG Xbox backwards compatibility crash?

* It crashes because RGLoader patches memory to be unprotected. If you want it to work, you will need to [uninstall](#uninstallation) this mod.

> My console reboots to regular XDK kernel, help?

* Make sure to check that you have correctly copied all files. If this does not help, this is most likely because you have a testkit, and like I mentioned, you will need to use a completely different method, which I cannot cover.

> Dashboard is missing some sounds!

* To fix this you need to disable xbox live DNS blocking in rgloader.ini. This is completely safe as your console is not able to connect to Xbox Live without doing additional modifications.

> Console is stuck on bootanim, wat do?

* You experienced a rare thing, but don't worry, there's an easy way to fix this:

### Method 1
You can use a recovery disc if you have one to delete the shadowboot file. Put the disc into your console, and let it reboot. After it reaches recovery screen, __DO NOT PRESS ANYTHING__. Instead, go over to your computer, and connect to the console with neighborhood, and delete the file.

### Method 2
TODO: nop shadowbooting in kdnet