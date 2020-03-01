# Udacity Claudio Acioli's Project 
### Refactor Udagram App into Microservices and Deploy



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