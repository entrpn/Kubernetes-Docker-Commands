#docker-commands

#bring up image. First time will take a long time as it brings in everything.

docker-compose up

#same as above run in background.
docker-compose up -d

#rebuild image
docker-compose up --build

#builds app again after having created it.

docker-compose build --no-cache

#If having issues with db, delete the container (Not the image) and recreate it. Thats the best way I found.

#delete containers

docker-compose rm -v

#view containers

docker ps -a

#stop container

docker stop <container_id>

#To additionally remove any stopped containers and all unused images (not just dangling images), add the -a flag to the command:

docker system prune -a

#logs
docker logs <container_id>

# Stop and Remove all containers
```
docker stop $(docker ps -aq)
docker rm $(docker ps -aq)
```
# Remove an image 

```
docker rmi <image_id>
```

# Remove all images

```
docker rmi $(docker images -q)
```
# Build and Run docker image

```
docker build -t <give_it_a_name> .
docker run -p 49160:8080 -d <give_it_a_name>
```
