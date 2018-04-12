# docker-commands

#bring up image. First time will take a long time as it brings in everything.

docker-compose up

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
