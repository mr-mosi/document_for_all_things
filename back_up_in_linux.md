## How to back up my linux system.

this command will backup all linux system exclude some unimportant files.

`sudo rsync -aAXv --delete --dry-run --exclude=/dev/* --exclude=/proc/* --exclude=/sys/* --exclude=/tmp/* --exclude=/run/* --exclude=/mnt/* --exclude=/media/* --exclude="swapfile" --exclude="lost+found" --exclude=".cache" --exclude=".encryptfs" <other thing else...> /soure /destination`

-a --archive	archive mode

-A --acls		preserve ACLs (Access Control Lists)

-X --xattrs		preserve extended attributes

-v --verbose	increase vebosity

--dry-run		simulate the backup

--delete/t		In the first backup it does noting and in the 					second backup it will backup only the diffrence 				between source and destination.