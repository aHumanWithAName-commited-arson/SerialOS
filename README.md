# SerialOS
A really light Arch-based Linux distro for my friend's ThinkPad.

**This build of Linux is designed to run the ThinkPad T450s ONLY. Do NOT run this distro on any other device**

## Installing
### Installing in QEMU
1)  Download [the ISO](https://github.com/aHumanWithAName-commited-arson/SerialOS/releases/download/v2026.01.31/serialos-2026.01.31-x86_64.iso)
2) Install QEMU
3) Run `qemu-system-x86_64 -cdrom path/to/SerialOS.iso`
4) If you want to install it in the VM then be sure to add a VHD

### Installing on real harrdware
1) Download [the ISO](https://github.com/aHumanWithAName-commited-arson/SerialOS/releases/download/v2026.01.31/serialos-2026.01.31-x86_64.iso)
2) Flash it to a USB using something like [balenaEtcher](https://etcher.balena.io/)
3) Boot the USB

## Default password(s)
### Default user account (the one you'll want to log in to when booting the live ISO/Installed system) 
User: serialos
Password: serialos

### Root (Do NOT log into this account, Use the serialos account)
user: root
password: root

## Getting the custom kernel onto the installed system
1) Download the following:

[linux-6.18.7.arch1-1-x86_64.pkg.tar.zst](https://github.com/aHumanWithAName-commited-arson/SerialOS/releases/download/v2026.01.31/linux-6.18.7.arch1-1-x86_64.pkg.tar.zst)

[linux-docs-6.18.7.arch1-1-x86_64.pkg.tar.zst](https://github.com/aHumanWithAName-commited-arson/SerialOS/releases/download/v2026.01.31/linux-docs-6.18.7.arch1-1-x86_64.pkg.tar.zst)

[linux-headers-6.18.7.arch1-1-x86_64.pkg.tar.zst](https://github.com/aHumanWithAName-commited-arson/SerialOS/releases/download/v2026.01.31/linux-headers-6.18.7.arch1-1-x86_64.pkg.tar.zst)

2) Open a terminal in the folder that the packages are located in.
3) Install the kernel: `sudo pacman -U linux-6.18.7.arch1-1-x86_64.pkg.tar.zst linux-headers-6.18.7.arch1-1-x86_64.pkg.tar.zst linux-docs-6.18.7.arch1-1-x86_64.pkg.tar.zst`
4) Update GRUB: `sudo grub-mkconfig -o /boot/grub/grub.cfg`
5) Reboot: `sudo reboot`
6) Once your back in the system, Run `uname -r` to check what kernel you have booted with. Expected output is `6.18.7-arch-1`

## Tips
* Run `serialos-install` to install serialos
* Run `nmtui` to connect to the internet
* Flatpak is installed by default!

## Known Bugs
* Most apps don't appear in the app menu
* Non-UEFI systems aren't supported
* Audio is broken (you'll have to fix it yourself for now)
* The installer installs the default kernel instead of the custom one
