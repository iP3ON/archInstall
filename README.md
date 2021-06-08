# archInstall
Basically an arch installation instruction.
----------------------------------------------------
This is a guide for me how to quickly install arch linux.
----------------------------------------------------

Steps:
1. timedatectl set-ntp true

2. (localectl list-keymaps | grep PL) --- loadkeys ...

3. pacman -Syyy

4. lsblk

5. cfdisk ...

6. mkfs.ext4 ...

7. mount ... /mnt

8. mkdir /mnt/boot

9. mount ... /boot

10. pacstrap /mnt base linux linux-firmware git vim intel-ucode

11. genfstab -U /mnt >> /mnt/etc/fstab (cat /mnt/etc/fstab)

12. arch-chroot /mnt

13. fallocate -l 2GB /swapfile

14. chmod 600 /swapfile

15. mkswap /swapfile

16. swapon /swapfile

17. vim /etc/fstab (add at the end "/swapfile none swap default 0 0")

Then git clone this repository,
chmod +x install.sh
./install.sh

The script takes care of the rest (change anything if necessary).
