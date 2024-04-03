---
layout: post
category: guides
---
## A guide for fast downloads off of Archive.org platform
## Table of contents
- [First method](#first-method)
- [Second method](#second-method)

---

## [First method](first-method)

We will use a program called [JDownloader2](https://jdownloader.org/jdownloader2) in this method.

First of all, download, and install this program until you can launch it. Allow it to update, if it asks. 

### Step 1

In main JDownloader2 screen, select option ``settings``, and Increase ``Max Chunks`` to 10 and ``Max Simultaneous Downloads`` to 16.

![guide_1](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/dl_guide/guide_1.png?raw=true)

### Step 2

Go to your desired archive.org link you want to download. In my case, we are downloading a [Most Wanted 2](https://archive.org/details/need-for-speed-most-wanted-2-ps3-prototype-collection) "a" build.

### Step 3

On the right side of the page, click on option ``Show all``. 

![guide_2](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/dl_guide/guide_2.png?raw=true)

### Step 4

You will see a list of files now. Scroll down to your desired build ("a" in my case), right click on it, and select ``Copy link`` *(this option may be called different in other browsers)*

![guide_3](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/dl_guide/guide_3.png?raw=true)

### Step 5

Now, go back to JDownloader2, and select ``LinkGrabber``. Chances are, it may automatically pick up the link from clipboard, and it will already be there. If not, simply press ``CTRL+V`` on your keyboard, to paste it in.

![guide_4](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/dl_guide/guide_4.png?raw=true)

### Step 6

Right click on the entry, and select ``Start downloads``. Change the download directory at the bottom, if needed.

![guide_5](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/dl_guide/guide_5.png?raw=true)

### Step 7 - The end

That's it! Now the file should be downloading at way faster speeds!

## [Second method](second-method)

This method will be slightly more advanced, as we will use a CLI program called [aria2c](https://github.com/aria2/aria2/releases/tag/release-1.37.0).

### Step 1

[Download](https://github.com/aria2/aria2/releases/tag/release-1.37.0) aria2c for your system (this guide was made for Windows systems).

### Step 2

Unpack the downloaded executable. You can place it anywhere, like in your ``Downloads`` directory. You could also add it to ``PATH`` so it can get called from anywhere. This guide will asume you placed it in ``Downloads``.

### Step 3

Go to your desired archive.org link you want to download. In my case, we are downloading a [Most Wanted 2](https://archive.org/details/need-for-speed-most-wanted-2-ps3-prototype-collection) "a" build.

### Step 4

On the right side of the page, click on option ``Show all``. 

![guide_2](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/dl_guide/guide_2.png?raw=true)

### Step 5

You will see a list of files now. Scroll down to your desired build ("a" in my case), right click on it, and select ``Copy link`` *(this option may be called different in other browsers)*

![guide_3](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/dl_guide/guide_3.png?raw=true)

### Step 6

Now go to your ``Downloads`` directory, select file path entry, enter ``cmd`` and press the ``Enter`` key. A command prompt window should show up.

![guide_6](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/dl_guide/guide_6.png?raw=true)

### Step 7

Now, enter the download command which goes like this:

```
aria2c <link goes here> -x 16 -s 16
```

and press ``Enter`` key.

![guide_7](https://github.com/dzastsed/dzastsed.github.io/blob/main/_pictures/dl_guide/guide_7.png?raw=true)

### Step 8 - The end

That's it! Now the file should be downloading at way faster speeds!