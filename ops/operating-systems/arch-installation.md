# Arch Installation

## Partition the disks
There are two partition modes: BIOS with MBR, UEFI with GPT. We choose the latter.

- Check the devices
``` shell
fdisk -l
```

- Enter the disk
``` shell
fdisk /dev/sda 
```

- Create a new empty GPT partition table
``` shell
g
```

- Add a new partition 1
``` shell
n
1
↓
+512M
```

- Add a new partition 3
``` shell
n
3
↓
+2G
```

- Add a new partition 2
``` shell
n
2
↓
↓
```

- Confirm
``` shell
p
```

- Write table to disk and exit
``` shell
w
```

## Format the partitions
- Format the EFI system partition
``` shell
mkfs.fat -F32 /dev/sda1
```

- Format the root (/) partition
``` shell
mkfs.ext4 /dev/sda2
```

- Format the EFI system partition
``` shell 
mkswap /dev/sda3
swapon /dev/sda3
```

## Mount
- Mount the file system on the root partition to /mnt
``` shell
mount /dev/sda2 /mnt
```

- Check
``` shell
ls /mnt
```

- Mount the boot
``` shell
mkdir /mnt/boot
mount /dev/sda1 /mnt/boot
```

## Install
- Install essential packages
``` shell
pacstrap /mnt base linux linux-firmware
```

## Configure the system
### Fstab
- Generate an fstab file
``` shell
genfstab -U /mnt >> /mnt/etc/fstab
```

- Check the resulting file
``` shell
vim /mnt/etc/fstab
```

### Chroot
- Change root into the new system
``` shell
arch-chroot /mnt
```

### Time zone
- Set the time zone
``` shell
ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
hwclock --systohc
```


## Root password




## Networks
pacman -S wpa_supplicant dhcpcd

systemctl enable dhcpcd@eth0.service

### SSH
pacman -Syy openssh

vim /etc/ssh/sshd_config



LoginGraceTime 120
PermitRootLogin yes
StrictModes yes

systemctl enable sshd.service 开机启动

systemctl start sshd.service 立即启动

systemctl restart sshd.service 立即重启

systemctl restart sshd.service




## References
> Installation guide  
https://wiki.archlinux.org/index.php/Installation_guide