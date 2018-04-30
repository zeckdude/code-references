## Docker

### Links
| Name          | Link                                                            |
|---------------|-----------------------------------------------------------------|
| Docker Command Line Documentation | https://docs.docker.com/engine/reference/commandline/docker/ |

<br>

#### Show docker containers
```shell
# Show all active containers
docker ps

# Show all active and non-active containers
docker ps -a
```

<br>

#### Download an image (if it hasn't been previously downloaded) and start a container based on it
```shell
# Run the latest version
docker run <image name>

# Specify the version to run
docker run <image name>:<version number>
# Example
docker run ubuntu:17.04

# Run the docker container in detach mode (prevent the terminal window from locking up while the container is running)
docker run -d <image name>
# Attach back to a container
docker attach <container id or name>
```

<br>

#### Download an image for later use
```shell
docker pull <image name>
```

<br>

#### Stop a docker container
```shell
docker stop <container id or name>
```

<br>

#### Remove a stopped container
```shell
# Remove a single container
docker rm <container id or name>

# Remove multiple containers
docker rm <container id or name> <container id or name> <container id or name>

# Alternatively, only the first three letters of the container id need to be provided
docker rm 345 a0b 773
```

<br>

#### List all images that have previously been downloaded from Docker Hub
```shell
docker images
```

<br>

#### Remove a previously downloaded image
```shell
docker rmi <image name>
```

<br>

#### Execute a command in the container
```shell
docker exec <container id or name> <command>
# Example (print contents of file)
docker exec 3eed277c1318 cat /etc/hosts
```

<br>

#### Start a container and open the shell
```shell
docker run -it <image name> <command>
# Example
docker run -it ubuntu bash
```

<br>

#### View the release details of the OS in the container
```shell
cat /etc/*release*
```

<br>

#### Exit out of shell inside container
```shell
exit
```


