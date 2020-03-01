# Udacity Claudio Acioli's Project 
### Refactor Udagram App into Microservices and Deploy

You can find the screenshots for this project [here](https://github.com/claudioacioli/udacity-microservice/tree/master/screeshot)

### Install On Docker

For clone this project and theirs submodules in your machine:

```bash
git clone --recurse-submodules https://github.com/claudioacioli/udacity-microservice.git
```

For build the images of this project:
```bash
docker-compose -f docker-compose-build.yaml build --parallel
```

Make sure you have below environments variables set:

```bash
export POSTGRESS_USERNAME=username
export POSTGRESS_PASSWORD=********
export POSTGRESS_DB=dabase
export POSTGRESS_HOST=host
export JWT_SECRET=secret
export AWS_REGION=region
export AWS_PROFILE=profile
export AWS_BUCKET=s3
```

For run:
```bash
docker-compose -f udacity-deployment/docker/docker-compose.yaml up
```

### Install On Kubernetes

Make the config files

```bash
kubectl apply -f udacity-developtment/k8s/env-config.yaml
kubectl apply -f udacity-developtment/k8s/env-secret.yaml
```

Make the deployments

```bash
kubectl apply -f udacity-developtment/k8s/backend-user-deployment.yaml
kubectl apply -f udacity-developtment/k8s/backend-feed-deployment.yaml
kubectl apply -f udacity-developtment/k8s/frontend-deployment.yaml
kubectl apply -f udacity-developtment/k8s/reverse-deployment.yaml
```

Make the services

```bash
kubectl apply -f udacity-developtment/k8s/backend-user-service.yaml
kubectl apply -f udacity-developtment/k8s/backend-feed-service.yaml
kubectl apply -f udacity-developtment/k8s/frontend-service.yaml
kubectl apply -f udacity-developtment/k8s/reverse-service.yaml
```

Expose the reverse proxy:

```bash
kubectl port-forward service/reverseproxy 8080:8080
```

Expose the frontend:

```bash
kubectl port-forward service/frontend 8100:8100
```
