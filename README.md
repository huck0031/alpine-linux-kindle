# Alpine Linux on Kindle
A project to bring modern Alpine Linux 32-bit to Kindle devices (running armhf/armv7), currently including Alpine versions v3.22 and v3.20 (more coming soon as I can test)

# Screenshots (WIP)

# Installation
1. Have a jailbroken Kindle, with KAUH + Kterm installed (be aware if your Kindle uses hard floats that you will need different versions or else Alpine's menu as well as Kterm will not launch)
2. Download alpine_kindle_kaul/ from schuhumi/alpine_kindle_kual and place in the extensions folder on Kindle
3. Replace deploy.sh in this folder with the modified deploy.sh from this repo (replaces where Alpine.zip/ext3 is pulled from in schuhumi's script, points to my repo's releases)
4. From KUAL, open the Alpine Linux menu and deploy the latest release, currently it will download from the latest stable included in this repo (Alpine v3.22, fastest and most stable from my testing compared to 3.20 and 3.21)

Afterwards, you are able to launch Alpine directly from KAUH

# Suggestions
- To disable the Kindle framework when running Alpine (frees more ram) run the following in Kterm:
```
mntroot rw
cp /mnt/us/alpine.conf /etc/upstart/
mntroot r
```
- I recommend disabling the Screensaver/lock until the onscreen keyboard is fixed on the lockscreen. Not doing this will result in being unable to unlock your Kindle after idle time (you can powercycle your Kindle when this happens).

# Why?
- I wanted a Kindle Scribe type of device, but already having a Kindle Paperwhite Gen 5 (Kindle 11th Gen) and some basic knowledge that all Kindles used Linux under the hood from past jailbreaking, I went on to figure out what my best option would be to turn the device into a basic handwritten note keeper, with the ability to export my drawings. Finding the amazing work several years ago from schuhumi, I found I could run Alpine Linux on almost any Kindle, however the releases included had not been updated in years, and caused me to run into several issues when running simple commands like apk (seg faults, signature issues, and other unexplainable issues I experienced when chrooting into the environment with packages over half a decade old). I decided to create new builds myself and make this repo for anyone who might benefit from a newer Alpine release. With Xournal++ on my Paperwhite 5, I'm able to take notes that are decent enough for my needs, without the need for a brand new device.

# Credits
using code from: [https://github.com/schuhumi/alpine_kindle](https://github.com/schuhumi/alpine_kindle) & relies on [https://github.com/schuhumi/alpine_kindle_kauh](https://github.com/schuhumi/alpine_kindle_kual)

# Troubleshooting
- If you are unable to load into Alpine *except* through a shell, ensure your DE is installed (run setup-desktop and install MATE, then run Alpine again from KAUH). You can also run startgui.sh from the chroot shell
- When logging out of the chrooted environment through X11, you may be brought to a blank screen forever. Simply hold the power button on your Kindle for about 10 seconds and it should reboot back to the Kindle framework without any lasting issues.
- The terminal is *probably* not broken, you just currently need to adjust the colors as the contrast of the Kindle cannot show the default color profile.

# TODO
- Include multiple (working) options in KAUH menu for version testing
- Auto set high-contrast theme, white background
- Auto set terminal colors to be visible
- Add additional auto installs including useful tools (plans to add flameshot in next release)
- Add patch to enable keyboard on lock screen (currently requires you to manually disable screensaver/auto-lock in order to not have to restart after 5 min of idle time
- ~~Improve Chromium performance - web browsing is a much slower experience with my builds compared to the older builds provided by schuhumi, however I am currently prioritizing security updates over performance~~
