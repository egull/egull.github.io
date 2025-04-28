# Pauli documentation and maintenance info


## Package installation
When configuring packages, ensure that the compilers are system compilers or that there's an explicit dependence in the resulting module file. Start with
```
module list
module unload X
```
and then load the modules that the build will depend on. For some packages we have prebuilt compilation / installation scripts. Have a look at 
```
/root/builds/build-all/script_gcc/
```
but most are built by hand and installed into directories under
```
/opt/ohpc/pub/
```
After installation, a module file needs to be created. Our module files are in
```
/opt/ohpc/pub/modulefiles/
```

## Security updates
Run the security updates as follows:

```
yum updateinfo list security
yum update --security
```   

## Backup information

We use [bacula](https://www.bacula.org/) for backups. The configuration file is in

 `/etc/bacula/bacula-dir.conf`

The tape pools are defined in

  `/etc/bacula/pools.conf`

## Warewulf admin info
Some additional info is here: `https://green-phys.org/pauli/`
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


## Node reboot and IPMI
Pauli has an IPMI network for the node. That's the 192.168.1.1XX network. Node 19, for instance, is at 192.168.1.119.
IPMI on these nodes can only be reached from the master. IMPI does require a password, which is stored in `/root/sec_data/` along with other secure data.
