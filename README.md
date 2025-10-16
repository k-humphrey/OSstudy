#These are my notes for my study sessions
left off on: 

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