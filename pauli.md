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

Recent command history is stored in `.bconsole_history`.


## Node reboot and IPMI
Pauli has an IPMI network for the node. That's the 192.168.1.1XX network. Node 19, for instance, is at 192.168.1.119.
IPMI on these nodes can only be reached from the master. IMPI does require a password, which is stored in `/root/sec_data/` along with other secure data.

## Checking kernel and bootloader
Sometimes, after security updates, the bootloader misbehaves and sets itself to a nondescript kernel. Use grubby to handle installing the bootloader and loading the right kernel
```
  ls -l /boot/vmlinuz-*
  grubby --default-kernel
  grubby --default-index
  grubby --set-default=/boot/vmlinuz-5.4.234-1.el8.elrepo.x86_64
```
## Unsticking a node stuck in drain state
If a node is stuck in drain state, but has otherwise recovered, it can be 'unstuck' with scontrol:
```
scontrol update NodeName=pauli18 State=DOWN Reason="undraining"
scontrol update NodeName=pauli18 State=RESUME
```
## Changing the partition wall time
If someone needs more time on a partition, update partition properties (like walltime) as
```
scontrol update partition=ludicrous MaxTime=4-00:00:00
```

## iommu and the GPU node
It seems that the GPU direct memory access needed for direct file access from the GPU is incompatible with some of the iommu settings. The solution is to disable iommu in the bios of the machine. The master has iommu disabled, but the GPU node has it enabled by default.

## updating and packaging the node image
Our node images are managed by warewulf. We are currently running Rocky Linux release 8.7 (Green Obsidian), and the original images are located in /opt/ohpc/admin/images/. 
