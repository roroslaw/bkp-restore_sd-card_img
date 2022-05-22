# bkp-restore_sd-card_img
## Backup and Restore sd-card image

### backup sd card
$ sudo dd if=/dev/rdisk2 of=sd-card_backup.img status=progress bs=16M

### compress image 
$ gzip -c sd-card_backup.img > sd-card_backup.img.gz

### unzip to original size
$ diskutil unmountDisk /dev/disk2

$ sudo gunzip sd-card_backup.img.gz

### flash with restored img
$ sudo dd if=sd-card_backup.img of=/dev/rdisk2  status=progress bs=16M
