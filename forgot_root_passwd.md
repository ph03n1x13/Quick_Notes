### Reset Forgotten Root Password in `Linux`
***
#### Context  
Reinstalled  `Debian 11` after an hdd crash moments back and forgotten to setup the root password and creating a user.

#### Steps
- Boot  
- Press `e` to edit commands in `grub` menu  
- Go to `linux /boot/vmlinuz-X.Y.Z root=UUID... ro` line.  
- Modify `ro` or `read-only` mode to `rw` or `read-write` mode.  
- Add `init=/bin/bash` at the end of the line for a single user root shell.  
- Mount root file system in `read-write` mode with `mount -n -o remount,rw /`  
- Reset the root password with `passwd`  
 

