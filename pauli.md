# Pauli documentation and maintenance info

## Backup information

We use [bacula](https://www.bacula.org/) for backups. The configuration file is in

 /etc/bacula/bacula-dir.conf

The tape pools are defined in

 /etc/bacula/pools.conf

bconsole starts the backup tape console information.

Recent command history is stored in .bconsole_history and lists the following:

help
quit
messages
status all
status all
messages
messages
status all
messages
messages
messages
list media
list media
purge volume=AJY181L8
purge volume=AJY182L8
messages
list media
purge volume=AJY183L8
purge volume=AJY184L8
purge volume=AJY185L8
purge volume=AJY186L8
purge volume=AJY187L8
purge volume=AJY188L8
purge volume=AJY189L8
list media
purge volume=AJY202L8
purge volume=AJY203L8
purge volume=AJY204L8
purge volume=AJY205L8
purge volume=AJY206L8
purge volume=AJY207L8
purge volume=AJY208L8
purge volume=AJY209L8
purge volume=AJY210L8
purge volume=AJY211L8
purge volume=AJY212L8
purge volume=AJY213L8
list media
list media
messages
status all
status schedule
help
disable schedule=WeeklyCycleInc
status schedule
umount
status all
status
6
help
list pools
relabel pool=Permanent
.
label barcodes pool=Permanent
yes
messages
list media
help
update volume=AJY264L8 enabled=0
update volume=AJY267L8 enabled=0
update volume=AJY270L8 enabled=0
update volume=AJY271L8 enabled=0
update volume=AJY274L8 enabled=0
list media
help
run job=pauli-master-perm-data-*
run job=pauli-master-perm-data-AZ
yes
run job=pauli-master-perm-data-af yes
run job=pauli-master-perm-data-gm yes
run job=pauli-master-perm-data-nt yes
run job=pauli-master-perm-data-uz yes
run job=pauli-master-perm-home yes
run job=pauli-master-perm-storage-AZ yes
run job=pauli-master-perm-storage-af yes
run job=pauli-master-perm-storage-gm yes
run job=pauli-master-perm-storage-nt yes
run job=pauli-master-perm-storage-uz yes
messages
status all
mount
messages
status all
messages
status all
messages
status all
messages
status all
umount
mount
label barcodes pool=TapesWeakly
yes
exit
messages
enable schedule=WeeklyCycleInc
status
6
status all
quit
status all
status all
messages
messages
status all
messages
messages
messages
list media
list media
purge volume=AJY181L8
purge volume=AJY182L8
messages
list media
purge volume=AJY183L8
purge volume=AJY184L8
purge volume=AJY185L8
purge volume=AJY186L8
purge volume=AJY187L8
purge volume=AJY188L8
purge volume=AJY189L8
list media
purge volume=AJY202L8
purge volume=AJY203L8
purge volume=AJY204L8
purge volume=AJY205L8
purge volume=AJY206L8
purge volume=AJY207L8
purge volume=AJY208L8
purge volume=AJY209L8
purge volume=AJY210L8
purge volume=AJY211L8
purge volume=AJY212L8
purge volume=AJY213L8
list media
list media
messages
status all
status schedule
help
disable schedule=WeeklyCycleInc
status schedule
umount
status all
status
6
help
list pools
relabel pool=Permanent
.
label barcodes pool=Permanent
yes
messages
list media
help
update volume=AJY264L8 enabled=0
update volume=AJY267L8 enabled=0
update volume=AJY270L8 enabled=0
update volume=AJY271L8 enabled=0
update volume=AJY274L8 enabled=0
list media
help
run job=pauli-master-perm-data-*
run job=pauli-master-perm-data-AZ
yes
run job=pauli-master-perm-data-af yes
run job=pauli-master-perm-data-gm yes
run job=pauli-master-perm-data-nt yes
run job=pauli-master-perm-data-uz yes
run job=pauli-master-perm-home yes
run job=pauli-master-perm-storage-AZ yes
run job=pauli-master-perm-storage-af yes
run job=pauli-master-perm-storage-gm yes
run job=pauli-master-perm-storage-nt yes
run job=pauli-master-perm-storage-uz yes
messages
status all
mount
messages
status all
messages
status all
messages
status all
messages
status all
umount
mount
label barcodes pool=TapesWeakly
yes
exit
messages
enable schedule=WeeklyCycleInc
status
6
status all
quit
history
show history
exit
