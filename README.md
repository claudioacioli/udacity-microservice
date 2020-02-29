

For clone this project and theirs submodules in your machine:

```bash
git clone --recurse-submodules https://github.com/claudioacioli/udacity-microservice.git
```

For build the images of this project:
```bash
docker-compose -f docker-compose-build.yaml build --parallel
```

For run:
```bash
docker-compose -f udacity-deployment/docker/docker-compose.yaml up
```