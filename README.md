# BasicLinuxDistro
A basic linux distro that is command line based

===== THESE COMMANDS MUST BE RAN IN THE boot-files FOLDER =====
to run it run this cmd

qemu-system-x86_64 boot 

you then need to pass the bzImage and init.cpio to do this you type

bzImage -initrd=init.cpio
