# Kernel-Stable

Custom kernel to go with Lilidog. Built with sources from https://www.kernel.org/ 

This is a "Long Term support" kernel I am using as a custom base, and is suitable for stable Debian. <br/>
Please note that these images are not patched by Debian to remove non-free items.

Both the unstable and stable kernel version should provide for various improvements throughout the build. <br/>
Find the unstable version here: https://github.com/sleekmason/Kernel-Unstable

__Features:__

- amd64
- Long term support kernel with the latest updates.
- Debugging mostly removed.
- Support for ntfs read and write.
- Timer frequency of 1000 vs 250 for desktop use.
- The ability to access the .config through /proc/config.gz (or dmesg in a terminal).
- Compressed cache for swap pages.
- More to come.

## Instructions

Download the file containing both the kernels and the headers and unzip the file. <br/>
Open a terminal in the resultant folder.
```sh
sudo dpkg -i *.deb
```
This will install the kernel and headers and will then update both your initramfs and then grub. Reboot.

If for some reason the kernel doesn't work for you, uninstall using apt:
```sh
sudo apt remove <Name of image>
```

## Build your own!

Lilidog comes with all the necessary packages to build your own kernel <br/>
Download and install one of the kernel and headers above so you have the basic configuration. <br/>
Boot into the kernel you just installed. <br/>
Download the tarball from https://www.kernel.org/ to match the version above. <br/>
Open a terminal. <br/>
Make a directory to work from:
```sh
mkdir kernel
```
```sh
cd kernel
```

Place the tarball into kernel and:
```sh
tar -xaf <linux-image-xx.xxxxx>
```
Use tab to autocomplete the name of the image.
Change directories into the resultant folder.
```sh
make menuconfig
```
This will grab the existing configuration and open up a dialog to make changes to the kernel.
Make any changes, save and close.
```sh
make -j3 deb-pkg
```

Go get a cup of coffee and hang out for a bit. while it makes. <br/>
Install like you did the first one. <br/>
Rinse and repeat.

There are numerous guides online, including my own. Feel free to email me for <br/>
a location to one of my own, or probably just search:)

sleekmason@gmail.com
