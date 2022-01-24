# hakchi4

This is a fork of hakchi2 ce (by TeamShinkansen)

This application can add more games (game ROMs) to your NES/SNES Classic Mini or Famicom Mini. All you need is to connect it to a Windows PC via Micro-USB cable. No soldering or disassembling required.

https://github.com/TeamNintenMod/hakchi4

### Features
Same As hakchi ce plus
* Smaller 

# Removed
* Translations
* And Such

## How do I use the tool?
Basically you just need to unpack it somewhere on your harddrive (installation is not required), run it, press “Add more games”, select some game ROMs and press “Synchronize”. The application will guide you through this process.

## How does the tool actually work?
You don’t need to worry about it. But if you really want to know, it’s using FEL mode. FEL is a low-level subroutine contained in the BootROM on Allwinner devices. It is used for initial programming and recovery of devices using USB. So we can upload some code into RAM and execute it. In this way we can read the Linux kernel (yes the NES Classic Mini and Famicom Mini runs an Linux operating-system), write kernel or execute kernel from memory without writing it to flash. So we can dump the kernel image of the NES Mini, unpack it, add some games and run a script which will copy them back to flash, repack, upload and execute. However, the games directory is on a read-only partition. Therefore we also need to create and flash a custom kernel with a special script that creates a sandbox folder on a writable partition and mounts it over the original games folder. This means that your original files are safe: you cannot delete or harm the original files in any way, even if you wanted. For kernel patching my application just executes other applications, which is why there is a “tools” folder.

## What if I have another question?
Many more commonly asked questions are answered in the FAQ:
https://github.com/TeamShinkansen/hakchi2/wiki/FAQ
