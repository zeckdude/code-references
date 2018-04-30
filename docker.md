## Docker

#### Show docker containers
```shell
# Show all active containers
docker ps

# Show all active and non-active containers
docker ps -a
```

<br>


#### Stop a docker container
```shell
docker stop <container id or name>
```

<br>

#### Remove a stopped container
```shell
docker rm <container id or name>
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

#### Download an image for later use
```shell
docker pull <image name>
```

<br>

#### Download an image (if it hasn't been previously downloaded) and start a container based on it
```shell
docker run <image name>
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
