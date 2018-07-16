## How to make bootable USB flash drive on any linux system

- check the partition name using this command `sudo fdisk -l` and in the bottm of the list or with size of the flash find it.

- `sudo dd bs=4M if=<file_location.iso> of=/dev/sdX status=progress && sync` this command make the USB. this take several minutes.

### After using

- after complition of copy make the USB default as in previous with this commands.
`sudo wipefs --all /dev/sdX`

`sudo cfdisk /dev/sdX` select `dos`. three time press `Enter` and final choose `write` create new partition on the flash.

- To format the partition to FAT use this command.`sudo mkfs.vfat -n 'USB_LABEL' /dev/sdX`. (maybe partition name changes after creation so check it before use the prvious name. check it with the `lsblk`)

## Make bootable USB with GUI

- using `Etcher` cross platform program. only can make linux USBs.