# Kernel-Stable
Custom kernel for Lilidog from https://www.kernel.org/
## Made for Lilidog.  
### This kernel should work for most Debian based systems.
Features:

- amd64
- Long term support kernel with the latest updates.
- Debugging mostly removed.
- support for ntfs read and write.
- timer frequency of 1000 vs 250 for desktop use.
- The ability to access the .config through /proc/config.gz (or dmesg in a terminal).
- Compressed cache for swap pages.
- more to come.

## Instructions
Download the Folder containing both the kernels and the headers.
Open a terminal in the resultant folder.
```sh
sudo dpkg -i *.deb
```
This will install the kernel and headers and will then update grub. Reboot.

If for some reason the kernel doesn't work for you, uninstall using apt:
```sh
sudo apt remove <Name of image>
```

## Build your own!

- Lilidog comes with all the necessary packages to build your own kernel
- Download and install one of the kernel and headers above so you have the basic configuration.
- Boot into the kernel you just installed.
- Download the tarball from https://www.kernel.org/ to match the version above.
- Open a terminal.
- Make a directory to work from:
```sh
mkdir kernel
```
```sh
cd kernel
```

- Place the tarball into kernel and:
```sh
tar -xaf <linux-image-xx.xxxxx>
```
Use tab to autocomplete the name of the image.
- Change directories into the resultant folder.
```sh
make menuconfig
```
This will grab the existing configuration and open up a dialog to make changes to the kernel.
- Make any changes, save and close.
```sh
make -j3 deb-pkg
```

- Go get a cup of coffee and hang out for a bit. while it makes.
- Install like you did the first one.
- Rinse and repeat.

There are numerous guides online, including my own. Feel free to email me for 
a location to one of my own, or probably just search:)

sleekmason@gmail.com
