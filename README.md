# Ansible LXC Clone
Ansible Playbook to quickly roll out a set of LXC Containers as clones from a template.
This PB has been developed and tested on Fedora 24

what does it do:
* It creates new LXC Containers as clones from a master
* BTRFS as backing store is used for FS-level snapshots
* the cloning function is coded as "shell", since the current lxc_container module for Ansible still trys to call "lxc-clone" although this command has been replaced with "lxc-copy"
* It injects a static Network Config.

requires:
* lxc, btrfs
* the template container must be stored on a btrfs subvolume (like /var/lib/lxc/template/rootfs)
