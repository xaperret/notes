uefi & bios => firmware of computer
hardware that will initialize the computer
multiple version of linux on computer is possible
grub allows to choose the version to load
bios is version before uefi
uefi emulates bios, but it will disappear soon
uefi load grub, grub loads a os

# Grub
is someting that implements a specification that tell how to load an OS on hardware.

grub has multiple stage
each stage must have some characteristics
for stage 2 -> assembler instructions that must be compiled by a compiler 
=> grub when it loads a program/exec it needs to have a specific signature (elf file), which in our case is our multiboot 

cfg -> menu with option

able to pass arguments to the os

grub loads a kernel and executes it
multiboot_info_t ==> structure with information for the os

## Load stuff with Grub

Create an ISO image