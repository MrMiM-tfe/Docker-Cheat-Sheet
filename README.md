## concepts
* persistent storage  
   use `volume` with `-v []:[]`

## commands
*  `pull`  
   get image from dockerHub

*  `run`  
   run image / get and run image  
   `--rm` remove container after run  
   `-it` contain interactive and tty  
   `-p [computer_port]:[container_port]` connect ports  
   `-v [system_dir]:[container_dir]` volumes  
   `--network [name]` connect to network (in container use container names for domain like: api:3000)  
   `-d` detach  

* `start [name]`  
   restart container

*  `exec [OPTIONS] [container_name/id] [command]`  
   execute command in container

*  `images`  
   show images  
   `rm` remove `-f` for force remove

*  `ps`  
   running containers  
   use `-a` to show exited containers  
   this contain command that was used

* `stop [container_id/name]`  
   stop container

*  `rm [container_id]`  
   remove container

*  `container prune`  
   remove all containers  
   `-a` for everything

*  `rmi [image_name]`  
   remove images

* `build [dir]`  
   build image from docker file  
   `-t` tag and name for image  
* `network`  
   `ls` get all networks  
   `create [name]` create network  


## DockerFile
```DockerFile
FROM <image_name> # start with image

WORKDIR <dir>

RUN <command> # run command in build time of image

ENV <name>=<value>

COPY <system_dir> <container_dir>

EXPOSE <container_port> # optional. just use for port mapping in docker desktop

CMD ["<command>", "<options>", ...] # run command when creating container from image
```
### Notes  
* dockerignore: file : `.dockerignore`

## Docker Compose
file : `docker-compose.yaml`  
command: `docker-compose` (`up`:run ,`down`: stop `--rmi all` remove all )
```yaml
version: "<version>"

services:
   <name>:
      image: <image name>
      build: <relive path to Docker File>
      container_name: <container name when ran>
      ports:
         - '<system_port>:<container_port>'
      volumes:
         - <system_path>:<container_path>
   <other_name>:
      # ...
      
```

## Errors
```
Error during connect: This error may indicate that the docker daemon is not running
```
just run docker desktop on windows

---
## Notes
* use `-L` in nodemon for working in docker
