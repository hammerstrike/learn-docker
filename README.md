Docker
===========================================================================
- Build Image
$ docker build <PATH_TO_Dockerfile> 

- Build image with name tag
$ docker build -t <IMAGE_TAG> <PATH_TO_Dockerfile>

- Delete image
$ docker image rm <IMAGE_ID>


- Docker run with dettached mode (-d) conatiner name --name and image name
$ docker run -d --name <CONTAINER_NAME> <IMAGE_NAME>

- Dcoker run with PORT
$ docker run -p 4000:3000 -d 

- Remove / delete container with force
$ docker rm <CONATAINER_NAME> -f

- List containers
$ docker ps

- ENV variable in docker container in dockerfile
ENV PORT 3000
EXPOSE $PORT

- Docker COmpose
$ docker-compose up -d 

=========================================================================
Example
=========================================================================
* build docker image
docker build -t image-docker-node-app .

* run docker container
docker run --env PORT=4000 -p 3000:4000 -d --name container-docker-node-app image-docker-node-app
docker run --env-file ./.env -p 3000:4000 -d --name container-docker-node-app image-docker-node-app

* delete container and volume associated
docker rm container-docker-node-app -fv

* Access container image shell
docker exec -it container-docker-node-app bash
printenv

* Volume 
docker volume ls
docker volume rm
docker volume prune
