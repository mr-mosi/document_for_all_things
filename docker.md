## Learning Docker

### There are different ways to use containers. These include:

1. **To run a single task**: This could be a shell script or a custom app.<br>
	- for example: `docker container run alpine hostname`
2. **Interactively**: This connects you to the container similar to the way you SSH into a remote server.<br>
	- for example: `docker container run --interactive --tty --rm ubuntu bash`<br>
		`--interactive` and `--tty` for run container in interactive way
3. **In the background**: For long-running services like websites and databases.


**Useful command**: `cat /etc/issue` will show which Linux distro is runing.

*the distribution of Linux inside the container does not need to match the distribution of Linux running on the Docker host.
However, Linux containers require the Docker host to be running a Linux kernel. For example, Linux containers cannot run directly on Windows Docker hosts. The same is true of Windows containers - they need to run on a Docker host with a Windows kernel.*

