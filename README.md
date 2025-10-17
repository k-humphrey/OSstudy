#These are my notes for my study sessions
left off on: 2.3.5 Running Bochs

What was I doing again?
1. Put together loader.s which is your "OS" that loads "CAFEBABE" into eax
    compiled loader.s with NASM into loader.o
    Put together linker for the "OS" called linker.ld (linker script!)
    linked loader.s with our linker.ld file into kernel.elf executable
    obtained GRUB's legacy stage2_eltorito, in binary form for easy reasons. (this is our bootloader)
    next time: build the iso file.

2. made the directory/directories iso/boot/grub for geniso command
    copied bootloader(grubs legacy stage2_eltorito) to the grub folder
    copied kernel (kernel.elf) to boot folder
    created menu.lst for the bootloader to find the kernel in grub folder
    generated iso with genisoimage
    Created the bochs config file bochsrc.txt
    Tried and failed to set up bochs emulation
    spent a couple hours trying to hack at it! Nothing was truly discovered.
    Time to take a break and watch some lectures and tutorials before I come back.
    
3. Okay, I wanted to try to fix any potential
    looming issues with Ubuntu and Virtual box, so I booted up this repo on a Ubuntu machine. Now I'm going to reinitialize everything and see if it made  a difference. and.. It did!! I also switched to Qemu because I found out there was just a serious issue with bochs, not my iso file.
    so now we build our qemu emulation by doing
    qemu-img create -f qcow2 mydisk.img 10G
    qemu-system-x86_64 -cdrom os.iso -boot d -m 512 -hda mydisk.img
    in the window we switch to View > compatMonitor0 and then type info registers
    you'll see that eax = cafebabe!