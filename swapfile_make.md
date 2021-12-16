 Adding Swap File to a Linux System 
 ***

Add a file as `swap` utility. 

- Create a `swapile` of 4Gib
``` bash
$ sudo dd if=/dev/zero of=/home/foysol/swapfile bs=1G count=4 status=progress

```  
- Move it to the `/` directory
```bash
$ sudo mv -v swapfile /
```  
- Change permission to `rw` only for `root` user
```bash
$ sudo chmod -v 600 /swapfile 
```  
- Change file property into swap
```bash
$ sudo mkswap /swapfile
``` 
- `swapon` the file
```bash
sudo swapon /swapfile
```  
- Edit `fstab` 
```bash
$ sudo nano /etc/fstab 
```  
- Append `swapfile` with the following values
```bash
/swapfile                                 none            swap       sw          0         0 
```  
- Check status
```bash
$ sudo swapon -s
```  
