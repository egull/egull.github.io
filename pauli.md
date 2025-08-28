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
  grubby --set-default=/boot/vmlinuz-5.4.257-1.el8.elrepo.x86_64
```
WARNING the '/data' drive is a zfs drive that requires a zfs module. Only the kernel 257 has that module installed. If another kernel is booted without this module, the /data drive will not appear.
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

## time server
The new time server ntpd is called chrony and polls its time from master, provided we specify
```
server 192.168.2.100 iburst
```
in the chrony config file at /etc/chrony.conf.

## updating and packaging the node image
Our node images are managed by warewulf. We are currently running Rocky Linux release 8.7 (Green Obsidian), and the original images are located in /opt/ohpc/admin/images/. The warewulf version we run is ancient (unclear which one) but some configuration is in /etc/warewulf/.

## preventing overheating
We used to set cpupower with the following trick: You can use the command cpupower frequency-set -g <governor_name> to switch to a different governor. Replace <governor_name> with the desired governor (e.g., performance, powersave, ondemand. We used powersave to keep the temperatures down. Likely this is no longer needed.

Hello, world!

## GPU PXEBoot
The GPU node is booted via pxeboot on old three-port ubiquity router. That router only has one job: providing the right host name for pulling the pxe image. The router username is emanuel. The configuration is part of the dhcp configuration, where the IP address is hardcoded. The router generates a .7 network and a .8 network, one on port 2 and the other one on port 3.

tftp then loads a pxeboot image from /var/lib/tftpboot/debug, currently it's called ipxe_GPU_v2.efi. This image is built in build/ipxe with command make bin-x86_64-efi/ipxe.efi EMBED=script.ipxe and then manually copied to the tftpboot directory.

The warewulf image itself needs to route traffic from master to the GPU node. This is done via ipip, with tunnel interfaces both on Pauli master and on GPU01. The GPU tunnel configuration is provisioned via warewulf and routes 192.168.* over to pauli master. The master tunnel config routes the .10 network back to the GPU01.
