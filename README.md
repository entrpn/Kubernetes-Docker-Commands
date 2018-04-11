# docker-commands

#bring up image. First time will take a long time as it brings in everything.

docker-compose up

#builds app again after having created it.

docker-compose build --no-cache

#If having issues with db, delete the container (Not the image) and recreate it. Thats the best way I found.
