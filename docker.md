## Learning Docker

### There are different ways to use containers. These include:

1. **To run a single task**: This could be a shell script or a custom app.<br>
	- for example: `docker container run alpine hostname`
2. **Interactively**: This connects you to the container similar to the way you SSH into a remote server.<br>
	- for example: `docker container run --interactive --tty --rm ubuntu bash`<br>
		`--interactive` and `--tty` for run container in interactive way. and `--rm` remove container after it stoped.
3. **In the background**: For long-running services like websites and databases. <br>
for example: 

```
docker container run \
	--detach \
	--name mydb \
	-e MYSQL_ROOT_PASSWORD=my-secret-pw \
	mysql:latest
```

- `--detach` will run the container in the background.
- `--name` will name it mydb.
- `-e` will use an environment variable to specify the root password (NOTE: This should never be done in production).

**Useful command**: `cat /etc/issue` will show which Linux distro is running.

*the distribution of Linux inside the container does not need to match the distribution of Linux running on the Docker host.
However, Linux containers require the Docker host to be running a Linux kernel. For example, Linux containers cannot run directly on Windows Docker hosts. The same is true of Windows containers - they need to run on a Docker host with a Windows kernel.*

**Some docker builtin commands:** `docker container logs` and `docker container top` the first shows logs of the running container and second will show processes are runinng on container.

**Run command in running container:** `docker exec mydb sh` will give us a interactive *shell* in *mydb* running container.

**Basic Docker File**
A simple docker file: 

```
FROM nginx:latest

COPY index.html /usr/share/nginx/html
COPY linux.png /usr/share/nginx/html

EXPOSE 80 443     

CMD ["nginx", "-g", "daemon off;"]
```

- `FROM` specifies the base image to use as the starting point for this new image you’re creating. For this example we’re starting from `nginx:latest`.
- `COPY` copies files from the Docker host into the image, at a known location. In this example, `COPY` is used to copy two files into the image: `index.html`. and a graphic that will be used on our webpage.
- `EXPOSE` documents which ports the application uses.
- `CMD` specifies what command to run when a container is started from the image. Notice that we can specify the command, as well as run-time arguments.

**Build Image**
- use the `docker image build`  command to create a new Docker image using the instructions in the Dockerfile.
- for example: `docker image build --tag $DOCKERID/linux_tweet_app:1.0 .`

- `--tag` allows us to give the image a custom name. In this case it’s comprised of our DockerID, the application name, and a version. Having the Docker ID attached to the name will allow us to store it on Docker Hub in a later step
- `.` tells Docker to use the current directory as the build context
Be sure to include period (`.`) at the end of the command.
- `--publish 80:80` using this tag for run the container this will allow traffic coming in to the Docker host on port 80 to be directed to port 80 in the container. The format of the --publish flag is host_port:container_port.

**Removing a container**
- use the `docker container rm --force linux_tweet_app` command to stop and remove a container.
- use the `--force` parameter to remove the running container without shutting it down.
- use the `docker container stop` to stop the container gracefully and then remove it with this `docker container rm`.

**Bind Mount**
- When we use a bind mount, a file or directory on the host machine is mounted into a container running on the same host.
- Bind mounts mean that any changes made to the local file system are immediately reflected in the running container.
- example of running with bind mount:

```
docker container run \
 --detach \
 --publish 80:80 \
 --name linux_tweet_app \
 --mount type=bind,source="$(pwd)",target=/usr/share/nginx/html \
 $DOCKERID/linux_tweet_app:1.0
```
- Modifing a file in local file system and seen it reflected in the running container, not actually changed the Docker image that the container was start from.
- use the ` docker image ls` to see list of Docker images was created. we may use with this parameters `docker image ls -f reference="$DOCKERID/*"`
