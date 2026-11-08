# Docker Images And Containers

## Images

Images are blueprints used to create containers.

Examples:

- nginx
- mysql
- ubuntu

List images:

```bash
docker images
```

Pull image:

```bash
docker pull nginx
```

---

## Containers

Containers are running instances of images.

Create container:

```bash
docker run nginx
```

List running containers:

```bash
docker ps
```

List all containers:

```bash
docker ps -a
```

Latest container:

```bash
docker ps -la
```

---

## Common Commands

Run container:

```bash
docker run -d --name web nginx
```

View logs:

```bash
docker logs web
```

Inspect container:

```bash
docker inspect web
```

Enter container:

```bash
docker exec -it web bash
```