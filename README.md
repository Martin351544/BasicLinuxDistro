# BasicLinuxDistro
A basic linux distro that is command line based

to get the basic setup look at Nir Litchmans video about how to make a basic linux distro (the setup is the same untill generating the boot file) https://www.youtube.com/watch?v=QlzoegSuIzg&t=588s


===== THESE COMMANDS MUST BE RAN IN THE boot-files FOLDER =====

To generate the boot file 

cd initramfs

chmod +x init

find . | cpio -o -H newc > ../init.cpio

cd ..

dd if=/dev/zero of=boot bs=1M count=1000

mkfs -t fat boot

syslinux boot

sudo mount boot m

sudo cp bzImage init.cpio m

sudo umount m


Then to boot using QEMU


qemu-system-x86_64 boot 

you then need to pass the bzImage and init.cpio to do this you type

bzImage -initrd=init.cpio


