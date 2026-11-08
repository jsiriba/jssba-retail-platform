# Day 02 - Docker Foundations

## Objectives

Learn the fundamental Docker concepts that underpin Kubernetes and AWX.

## Topics Covered

- Docker Images
- Docker Containers
- Docker Logs
- Docker Inspect
- Docker Exec
- Container Networking
- Port Publishing
- Docker Volumes
- Docker Compose

## Key Concepts

### Image

A blueprint used to create containers.

Examples:

- nginx
- mysql
- ubuntu

Commands:

```bash
docker images


```
## Container

A running instance of an image.

Commands:
> docker ps
> docker ps -a


 
## Image vs Container


Image = Blueprint

Container = Running instance

## Lessons Learned

Containers are temporary.

Volumes are persistent.


## Exercises
- Ran hello-world container
- Ran nginx container
- Investigated mysql startup failure
- Published nginx using port mapping
- Created persistent Docker volume
- Created Docker Compose file

## Next Steps

- Docker Networking
- Kubernetes
- Kind
- AWX