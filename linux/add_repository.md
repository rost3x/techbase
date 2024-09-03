1. Mount the iso disc to your hypervisor or put it on the usb stick and plug it into your machine.
2. Login as root and use `lsblk` make sure it's visible.
3. Modify the fstab file to create persistent mounting `/etc/fstab`
4. Create `/repos` directory
5. Add the following line:      
    `/dev/sr0/  /repos  iso9660 defaults 0 0`. Save and quit
6. Reload the system daemon `systemctl daemon-reload`
7. Mount the disk `mount -a`
8. Go to `/repos` to make sure you can see the directories
9. Add the repositories to `dnf` 
    `dnf config-manager --add-repos=///repos/BaseOS`
    `dnf config-manager --add-repos=///repos/AppStream`
10. Add the following line to `/etc/yum.repos.d/repos_AppStream.repo` and `/etc/yum.repos.d/repos_BaseOS.repo`
    `gpgcheck=0`
