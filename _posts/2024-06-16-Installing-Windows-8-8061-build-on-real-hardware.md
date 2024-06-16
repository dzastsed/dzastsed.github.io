---
layout: post
categories: stories-guides
---
## Table of contents:
- [Backstory](#backstory)
- [The problem](#the-problem)
- [The result](#the-result)
- [Conclusion](#conclusion)


## [Backstory](#backstory)
So a while back a very early ARM32 build of Windows 8 was released which still looks like Windows 7 (which arguably has the best theme apart from Vista) and of course, me being me, I wanted to run it on real hardware, not QEMU. Sourcing a Surface RT tablet together with charging brick for a good price (for some reason people want 80 euros for it!). Anyway about a month ago I finally managed to get it for quite cheap and finally went to work.
## [The problem](#the-problem)
After a bit of research, it turned out that 8061 build is only available as install.wim dump, which also needs some patches to run on real hardware - luckily prepatched binaries (acpi.sys, sdbus.sys drivers and dwm.exe for aero effects without driver - this makes performance terrible though) exist but not the wim file, so figuring out how to patch it was fun as well. I will upload whole installer USB later.

Then another problem came - how to install it? There's only guides for QEMU with whole pre-made hard drive images, but not installers or anything. So I did the most "logical" step - took Windows 10 installer usb (which I tried as well, the only leaked Windows 10 build for ARM32), and swapped it's own install.wim with my patched one.
## [The result](#the-result)
Well believe it or not, after installation it did boot! Unfortunately the betta fish bootscreen was replaced by stock Surface bootscreen but eh, whatever, as long as it works.

Anyway, there's yet another problem - due to this build being so early, it barely supports this hardware, so touchscreen or attachable keyboard obviously don't work. So I was stuck on this part:
![surface_1](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/surface_pics/surface_1.png?raw=true)

As I was in my university dorm with no USB keyboard, I could not proceed further. USB mouse would not work either, so this had to be slept on for a few weeks. Fast forward to two days ago and I am back on this project - got USB keyboard, buuut.... stil nothing. So what's the issue here?
![surface_2](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/surface_pics/surface_2.png?raw=true)

Okay, so I need to use an USB hub, no problem. But wait, it still does not work? 

Thank god I had some common sense - apparently this tablet, for whatever reason, would not output enough power for keyboard while booted in Windows, so I needed a powered hub! And sure enough, this was finally enough, and I was able to finish the OOBE and it finally booted into the desktop!
![surface_3](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/surface_pics/surface_3.jpg?raw=true)

## [Conclusion](#conclusion)
So, to sum up, what is required to run this build?
 - You need ARM32 installation media - I used Windows 10 media builder from [Windows RT Devices GitBook](https://windows-rt-devices.gitbook.io/windows/tools/windows-media-builder), chose 4th option in setup mode and then swapped install.wim around. You can use [this](https://archive.org/details/win-8061-iso) ISO if you want.
 - A powered USB hub and USB keyboard + mouse.
 - Tablet __MUST NOT__ have Yahallo jailbreak installed - this will make this build unbootable. Golden keys can be installed if you want.

Huge thanks to Betawiki discord members for helping me with stupid questions when trying to run this build!
