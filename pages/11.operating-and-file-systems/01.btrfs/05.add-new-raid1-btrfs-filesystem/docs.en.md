---
title: 'Add new raid1 btrfs filesystem'
taxonomy:
    category:
        - docs
child_type: docs
routes: {  }
---

Assuming you have one btrfs partition used as root (/) and you want to create RAID 1 using another partition

1. Check btrfs filesystem

        btrfs filesystem show

2. Add another partition to root with force

        btrfs device add /dev/sdb1 / -f

3. Check filesystem

        btrfs filesystem show

    Result is something like
    
    ```
    Label: none  uuid: 2601731d-934b-4c18-90fa-aa9cc61ced98
    Total devices 2 FS bytes used 6.47GiB
    devid    1 size 119.24GiB used 10.02GiB path /dev/sda2
    devid    2 size 119.24GiB used 0.00B path /dev/sdb1
    ```

4. Start RAID1 in root (/)

        btrfs balance start -dconvert=raid1 -mconvert=raid1 /

6. Check file system usage

        btrfs filesystem df /

    When balancing is going on there is warning
    
    ```
    WARNING: Multiple block group profiles detected, see 'man btrfs(5)'
    WARNING:    Data: single, raid1
    ```