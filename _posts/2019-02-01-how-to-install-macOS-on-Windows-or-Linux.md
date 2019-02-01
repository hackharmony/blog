---
layout: post
title: How to install Apple macOS on Windows or Linux in a virtual machine
---

I can only guarantee this working as of the time that this was posted. It's a complete hack, but it works. I also was able to do the same thing on GNU/Linux (Ubuntu 18.04) with the exact same method.

The biggest downside is that there is *no* way to get macOS on VMWare (or Virtualbox) to use multiple monitors.

This can be done without having to trust any sketchy, malware-laden torrents. You can use a genuine macOS image from Apple and a genuine VMWare Player.

# 1. Download genuine MacOS from the App Store on a real Mac

Acquire access to a genuine Mac temporarily.

Go in the App Store, search for "MacOS", and hit download. It will save to "/Applications/Install macOS High Sierra.app". The installer will automatically open as if you are updating the computer you're using--just ⌘Q out of it.

Caveat: I tried to do this step in my VM install of macOS, and was only able to get a ~17MB "Install macOS High Sierra.app" from the App Store. It probably was because there was very little space left on the drive, so make sure the Mac you're using has at least 10GB of free storage space. The image from the App Store for High Sierra is close to 6GB.

# 2. Create a bootable ISO on the Mac

Follow [Step 1 of these instructions from HowToGeek](http://archive.is/Mqr8I). If you're reading this in the future, and using a future version of macOS, be sure to change "/Applications/Install\ macOS\ High\ Sierra.app" to the actual path of your new installation. (Don't just blindly copy and paste the terminal commands here.)

You can't do this on Linux or Windows. Making the bootable ISO depends on some proprietary tools from Apple that come with the OS. If you don't have `hdiutil` or `asr` on the Mac you're using, make sure to install XCode Command Line Tools from the App Store.

If you want to skip steps 1 and 2 here, you can just [download the High Sierra image I made](https://drive.google.com/open?id=1BFmaCqMN2ur9ZQumw3EXbsYPyky5h73l). (I would prefer you actually go through the work above, though, rather than trusting binaries from random blogs.)

# 3. On Windows (or Linux), install VMWare Player

[It's free (as in beer)](https://www.vmware.com/products/workstation-player.html) for personal, non-commercial use. The one I used was the current version at the time of writing, VMWare Workstation Player 14.

# 4. Install the VMWare unlocker hack

It's [on Github and open source](https://github.com/DrDonk/unlocker). Normally VMWare won't run macOS on non-Apple devices, as that violates Apple's EULA. Follow the instructions on there. This also installs the Guest Additions so that you can open macOS at full screen resolutions.

Without this hack, none of this would work.

# 5. Go through the tedious steps of configuring the VM

![](https://i.imgur.com/Z6YsUqh.jpg)

![](https://i.imgur.com/8Hd1uU5.jpg)

![](https://i.imgur.com/ogYT2oV.jpg)

![](https://i.imgur.com/ogYT2oV.jpg)

![](https://i.imgur.com/mT1jFMF.jpg)

![](https://i.imgur.com/as4YMpX.jpg)

![](https://i.imgur.com/kKXtMFt.jpg)

![](https://i.imgur.com/K0z8DOB.jpg)

![](https://i.imgur.com/qQZQ4JY.jpg)

![](https://i.imgur.com/5gevmp1.jpg)

![](https://i.imgur.com/GSKJxcl.jpg)

![](https://i.imgur.com/nhYbZHs.jpg)

![](https://i.imgur.com/GRoslDI.jpg)

![](https://i.imgur.com/A5J3U4D.jpg)

![](https://i.imgur.com/9ZgQLQd.jpg)

![](https://i.imgur.com/egVdBfS.jpg)

![](https://i.imgur.com/7eKbeuU.jpg)

![](https://i.imgur.com/Q4yjEQJ.jpg)

![](https://i.imgur.com/09o3q8Y.jpg)

![](https://i.imgur.com/xvROSla.jpg)

![](https://i.imgur.com/l4PikGT.jpg)

![](https://i.imgur.com/lFrrURe.jpg)

![](https://i.imgur.com/riDn1Ec.jpg)

![](https://i.imgur.com/9UbIgDh.jpg)

You can handle it from there.

If the display resolution refuses to change to your actual high resolution, try:

`$ sudo defaults delete /Library/Preferences/com.apple.windowserver.plist DisplayResolutionEnabled`

and restart the VM. The HiDPI setting will be gone.

# 6. You're in! You're officially in macOS! 🎉🎉🎉🙌

You can do pretty much anything you could do on a genuine Mac…well, except some animations will cause the VM to crash because VMWare has a hard limit on the video memory you can allocate to it. Just disable all the fancy animations and don't play videos in your VM. This isn't a good idea for regular computing usage---Windows or Linux are much smoother. You should only do this for things that absolutely require macOS, like running XCode for example.
