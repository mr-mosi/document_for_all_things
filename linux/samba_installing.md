## Samba

###### As I found out samba is a service for resource sharing between linux and windows machines.

Steps to installing samba:
- For last version using apt to install.
- For earlier versions download .tar.gz files form samba [site](https://download.samba.org/pub/samba/stable/).
- To install samba from .tar.gz file read this [page](https://wiki.samba.org/index.php/Build_Samba_from_Source).
	- First install requirments.
	- Go to ../samba_*/source3
	- ./configure
	- make
	- sudo make install
	- export path like in the guide page
	- go to /usr/local/samba/sbin and then ./smbd
	- after getting error message copy smb.conf.defualt form ../samba_*/examples/ to /usr/local/samba/etc/
	- again run ./smbd from /usr/local/samba/sbin