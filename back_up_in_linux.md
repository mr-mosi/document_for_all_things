## How to back up my linux system.

rsync is very doncky program and i vary try to exclude all except some folders and it not works in this way. best way is exclude folders in a file and then do this.

the command that work for me is this.

```
sudo rsync -aAXv --delete --exclude-from=Desktop/includes.txt  /home/ /media/$USER/Data/linux/backup
```

this command will backup all linux system exclude some unimportant files.

```
sudo rsync -aAXv --delete --dry-run --exclude=/dev/* --exclude=/proc/*  --exclude=/sys/* --exclude=/tmp/* --exclude=/run/*  --exclude=/mnt/* --exclude=/media/* --exclude="swapfile"  --exclude="lost+found" --exclude=".cache" -exclude=".encryptfs"  <other thing else...> / /destination  
```

```
-a	--archive	archive mode
-A	--acls		preserve ACLs (Access Control Lists)
-X	--xattrs	preserve extended attributes
-v 	--verbose	increase vebosity

--dry-run		simulate the backup
--delete		In the first backup it does noting and in the second backup it will backup only the	diffrence between source and destination.
```