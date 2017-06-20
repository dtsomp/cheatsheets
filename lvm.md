# LVM

## Installation 

    apt-get install lvm2

## Basic usage

Format a disk for lvm use:

    fdisk /dev/sdb
    n               (new partitions)
        p           (primary)
        1           (partition number)
        [enter]     default first sector
        [enter]     default last sector
    t               (change partition id)
        (1)         (select the partitions if there are >1)
        8e          (hex code for LVM partition)
    p               (overview)
    w               (write partition table)

Create physical LVM volume

    pvcreate /dev/sdb1
    pvdisplay

    (if "no device found", run "partprobe")

Create volume group

    vgcreate datavg /dev/sdb1 [ /dev/sdbx /dev/sdby etc ]
    vgdisplay

Extend volume group

    vgextend datavg /dev/sdc1
    vgdisplay

    lvextend -l +100%FREE datavg

Create logical volume

    lvcreate --name loglv --size 1023G datavg
    lvcreate --name loglv -l 100%FREE datavg

    lvdisplay

Format partition

    mkfs.ext4 -L logs /dev/datavg/loglv

Mount in /etc/fstab

    # /etc/fstab
    /dev/datavg/datalv /mnt/registy ext4 defaults 0 2


## Special cases

Shrink LV

    # Unmount the partition

    umount /dev/mapper/datavg-datalv

    # Check fs

    e2fsck -f /dev/mapper/datavg-datalv

    # Shrink to target size of  3G

    lvreduce --resizefs -L 3G /dev/mapper/datavg-datalv

    # Check fs again before mounting

    e2fsck -f /dev/mapper/datavg-datalv

Create LVM snapshot

    # LVM snapshots need to be big enough to contain all changes during this procedure.
    # Size of changes != size of volume
    lvcreate --snapshot --size=1G --name=SNAPNAME /dev/mapper/datavg-datalv

    # Mount the snapshot
    mount /dev/mapper/datavg-SNAPNAME /mnt/mountpoint

    # Rsync stuff out of the snapshot

    # Unmount and remove
    umount /mnt/mountpoint
    lvremove /dev/mapper/datavg-SNAPNAME
