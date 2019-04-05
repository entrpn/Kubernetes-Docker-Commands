# Kubernetes

The following link shows how to deploy locally: 

https://kubernetes.io/docs/tutorials/hello-minikube/

The following link has good examples of config files for auth, deployments and services as well as canary and blue-green updates 

https://github.com/entrpn/orchestrate-with-kubernetes/tree/master/kubernetes

### Isolate environments by creating a namespace

```kubectl create ns production```

### Describe deployment status

```kubectl describe pod```

### Create deployment

```kubectl create deployment hello-python-tf --image=gcr.io/chatbot-7b96c/hello-python-tf:v1```

### Delete deployment

```kubectl delete deployment hello-python-tf```

### Edit deployment

```kubectl edit deployment hello-python-tf```

### Create Service

```kubectl expose deployment hello-python-tf --type=LoadBalancer --port=8080```

### Delete Service

```kubectl delete service hello-python-tf```

### View Rollout history

```kubectl rollout history deployment/hello-python-tf```

### Pause a rollout

```kubectl rollout pause deployment/hello```

### Resume rollout

```kubectl rollout resume deployment/hello```

### Status of rollout

```kubectl rollout status deployment/hello```

### Roll back to previous version

```kubectl rollout undo deployment/hello```


### Upload docker image to registry 

https://cloud.google.com/kubernetes-engine/docs/tutorials/hello-app#step_1_build_the_container_image

This must be called from where the Dockerfile is located

```docker build -t gcr.io/chatbot-7b96c/hello-python-tf:v1 .```

Authorize

```gcloud auth configure-docker```

Push

```docker push gcr.io/chatbot-7b96c/hello-python-tf:v1```

# Docker

### bring up image. First time will take a long time as it brings in everything.

docker-compose up

#### same as above run in background.
docker-compose up -d

#### rebuild image
docker-compose up --build

### builds app again after having created it.

docker-compose build --no-cache

- If having issues with db, delete the container (Not the image) and recreate it. Thats the best way I found.

### delete containers

docker-compose rm -v

### view containers

docker ps -a

### stop container

docker stop <container_id>

- To additionally remove any stopped containers and all unused images (not just dangling images), add the -a flag to the command:

docker system prune -a

### logs
docker logs <container_id>

### Stop and Remove all containers
```
docker stop $(docker ps -aq)
docker rm $(docker ps -aq)
```
### Remove an image 

```
docker rmi <image_id>
```

### Remove all images

```
docker rmi $(docker images -q)
```
### Build and Run docker image

```
docker build -t <give_it_a_name> .
docker run -p 49160:8080 -d <give_it_a_name>
```
