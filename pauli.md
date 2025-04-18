# Pauli documentation and maintenance info

## Backup information

We use [bacula](https://www.bacula.org/) for backups. The configuration file is in

 `/etc/bacula/bacula-dir.conf`

The tape pools are defined in

  `/etc/bacula/pools.conf`

`bconsole` starts the backup tape console information.

The most useful commands are:

```
 list media
 messages
 status all
 status schedule
 mount / umount
 label barcodes pool=TapesWeakly
 enable schedule=WeeklyCycleInc
```


Our backups currently hang as follows:

```
18-Apr 01:49 bacula-sd JobId 2383: Job pauli-master-tape-storage-af.2025-04-14_11.03.00_59 is waiting. Cannot find any appendable volumes.
Please use the "label" command to create a new Volume for:
    Storage:      "ULTRIUM-HH8" (/dev/tape/by-id/scsi-35000e111c80e8001-nst)
    Pool:         TapesWeakly
    Media type:   LTO-8
```

Recent command history is stored in `.bconsole_history`.
