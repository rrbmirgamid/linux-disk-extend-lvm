```console
root@srvub20:/home/ub20# lvdisplay
  --- Logical volume ---
  LV Path                /dev/ubuntu-vg/ubuntu-lv
  LV Name                ubuntu-lv
  VG Name                ubuntu-vg
  LV UUID                VIzz3d-mcqu-QBms-j83h-uPhn-neZW-Gy3DXK
  LV Write Access        read/write
  LV Creation host, time ubuntu-server, 2020-07-03 02:38:29 +0000
  LV Status              available
  # open                 1
  LV Size                <4.98 GiB
  Current LE             1274
  Segments               1
  Allocation             inherit
  Read ahead sectors     auto
  - currently set to     256
  Block device           253:1

```

```console
root@srvub20:/home/ub20# lvextend /dev/ubuntu-vg/ubuntu-lv -L +1G
  Size of logical volume ubuntu-vg/ubuntu-lv changed from <4.98 GiB (1274 extents) to <5.98 GiB (1530 extents).
  Logical volume ubuntu-vg/ubuntu-lv successfully resized.
```

```console
root@srvub20:/home/ub20# lvdisplay
  --- Logical volume ---
  LV Path                /dev/ubuntu-vg/ubuntu-lv
  LV Name                ubuntu-lv
  VG Name                ubuntu-vg
  LV UUID                VIzz3d-mcqu-QBms-j83h-uPhn-neZW-Gy3DXK
  LV Write Access        read/write
  LV Creation host, time ubuntu-server, 2020-07-03 02:38:29 +0000
  LV Status              available
  # open                 1
  LV Size                <5.98 GiB
  Current LE             1530
  Segments               1
  Allocation             inherit
  Read ahead sectors     auto
  - currently set to     256
  Block device           253:1

```

```console
root@srvub20:/home/ub20# resize2fs /dev/ubuntu-vg/ubuntu-lv
resize2fs 1.45.5 (07-Jan-2020)
Filesystem at /dev/ubuntu-vg/ubuntu-lv is mounted on /; on-line resizing required
old_desc_blocks = 1, new_desc_blocks = 1
The filesystem on /dev/ubuntu-vg/ubuntu-lv is now 1566720 (4k) blocks long.
```
