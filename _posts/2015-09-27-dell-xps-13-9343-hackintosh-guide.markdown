---
author: livingmethod
comments: true
date: 2015-09-27 21:22:08+00:00
layout: post
link: http://blog.jblee.kr/2015/09/27/dell-xps-13-9343-hackintosh-guide/
slug: dell-xps-13-9343-hackintosh-guide
title: Dell Xps 13 (9343) Hackintosh Guide
wordpress_id: 104
---




<blockquote>from : http://www.tonymacx86.com/yosemite-laptop-support/163689-dell-xps-13-5th-generation-setup-9343-help-10.html</blockquote>




<blockquote>Now that I got my Dell XPS 9343 up and running quite smooth but not 100% by any mean. I see that a lot of people having a difficult time to get it up an running so I just want to share my experience.

First of all I would like to thanks Rehabman for his GUIDE and Frizinko for his EFI folder.

Here are steps that I took:
I didn't have to modified DVMT at all my XPS came with Windows 8.1 and I check Dedicated Video Memory and it is 0 MB.
When I installed Windows 10 Preview on it the Dedicated Video Memory shown up at 128 MB so that's why I didn't do anything with DVMT.

1. I download the Frizinko's EFI folder from here [[GUIDE] Intel HD Graphics 5500 on OS X Yosemite 10.10.3](http://www.tonymacx86.com/yosemite-laptop-support/162062-guide-intel-hd-graphics-5500-os-x-yosemite-10-10-3-a-6.html)

2. I setup USB installation using Rehabman here: [http://www.tonymacx86.com/yosemite-l...over-uefi.html](http://www.tonymacx86.com/yosemite-laptop-support/148093-guide-booting-os-x-installer-laptops-clover-uefi.html)

3. After USB is ready to be use to install Yosemite to the HDD I delete the EFI folder in the USB and replace it with Frizinko's EFI folder. This very imported you need to edit Frizinko's "config.plist" make sure "Graphics""Inject""Intel" is "FALSE" if it's "true" the screen will go black.

4 I follow Rehabman's guide until it finished install files on the HHD I install Clover to HDD this time I also selected "EmuVariableUefi-64.efi", "Install RC scripts on target volume" and "Install Clover Preference Pane".

5 Again I deleted EFI folder that Clover just installed to HDD and replaced with EFI folder in the USB then I reboot the system without USB just to make sure that it will boot fine.

6. after it boot back up without USB then I install wifi kext first make sure that I have an internet access before I continue. Without the internet access the IOKit patch won't work.

6.1 Open Terminal and do the IOKit patch with these commands:

sudo perl -i.bak -pe 's|\xB8\x01\x00\x00\x00\xF6\xC1\x01\x0F\x85|\x33\x C0\x90\x90\x90\x90\x90\x90\x90\xE9|sg' /System/Library/Frameworks/IOKit.framework/Versions/Current/IOKit

sudo codesign -f -s - /System/Library/Frameworks/IOKit.framework/Versions/Current/IOKit

Then I used Clover Configurator(You can use command for that) to mount EFI folder and edit "config.plist" "Graphics""Inject""Intel" to "True". Reboot the system

7. Now my system should boot up with full graphics.

8. Now I install bcm4352.kext for wifi, BrcmPatchRAM.kext for Bluetooth, VoodooHDA.kext for sound, ACPIBatteryManager.kext for battery status and AppleIntelBDWGrphicsFrambuffer.kext for graphics.

DONE

That's I did with my XPS like I said this is not 100$ working system it's still a lot of work to do and fix.

Here are some problems that I encounter.
Sounds: works most of the time but some time after reboot I lost the sound have to reboot again.
Sleep: works but some time it doesn't go to deep sleep and if I closed the lid the screen will stay black and I have to shut it down.
Webcam: the system recognized it but none of the apps recognized they all said I don't have a camera.
Graphics: I can't use Safari after I open it for a few minutes the screen goes crazy I have to reboot to fix it so I have to use Chrome instead.
I'm sure it will be some other problems that I don't know but other than that it's running very smooth all day. I would say it's about 80% stable and fast.

That's all I can tell you so please don't ask me about technical questions I am a noob and new to Hackintosh. Just want to share my experience that's all.

Thanks,
Lopburi</blockquote>









![Attached Files](http://www.tonymacx86.com/images/misc/paperclip.png) Attached Files



	
  * ![File Type: zip](http://www.tonymacx86.com/images/attach/zip.gif) [Kexts.zip](http://www.tonymacx86.com/attachments/yosemite-laptop-support/139673d1433281192-dell-xps-13-5th-generation-setup-9343-help-kexts.zip) (1.33 MB, 117 views)



