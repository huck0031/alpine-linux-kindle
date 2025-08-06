# Alpine Linux on Kindle
Binary releases (testing) for Alpine Linux armhf/armv7 including versions v3.20, v3.21 and more coming soon as I can test (currently testing for Kindle 11th Gen Paperwhite)

# Installation
1. Have jailbroken kindle, with KAUH and Kterm installed (be aware if your kindle uses hard floats that you will need different versions)
2. Download alpine_kindle_kaul from schuhumi/alpine_kindle_kual and place in the extensions folder on kindle
3. Replace my customized deploy.sh script (replaces release location of Alpine.zip/ext3 to my repo)
4. From KUAL open Alpine Linux and deploy the latest release, it will download from the latest stable included in this repo (currently Alpine v3.20)
5. Drop into the Alpine Linux shell from KUAL, run setup-desktop and install MATE DE (others not tested)
6. Execute startgui.sh

# Suggestions
To disable the Kindle framework when running Alpine (frees more ram) run the following in Kterm:
```
mntroot rw
cp /mnt/us/alpine.conf /etc/upstart/
mntroot r
```
# Why?
Thanks to the amazing work several years ago from schuhumi, you can run Alpine Linux on almost any Kindle, however the releases included have not been updated and can cause you to run into several issues (primarily seg faults, signature issues due to the drastic deviation from the typical kernel version a kindle and the one you are chrooting into) so I decided to make this repo for myself and anyone who might benefit from a newer Alpine release.

# Credits
using code from: https://github.com/schuhumi/alpine_kindle

# TODO
Include multiple options in KAUH menu for version testing, add additional auto installs for useful tools
