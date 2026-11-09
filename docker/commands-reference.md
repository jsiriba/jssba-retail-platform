# Docker Commands Reference

## Image Commands

Pull image:

```bash
docker pull nginx
```

List images:

```bash
docker images
```

---

## Container Commands

Create container:

```bash
docker run nginx
```

Create detached container:

```bash
docker run -d --name web nginx
```

List running containers:

```bash
docker ps
```

List all containers:

```bash
docker ps -a
```

Show latest container:

```bash
docker ps -la
```

Stop container:

```bash
docker stop web
```

Remove container:

```bash
docker rm web
```

Force remove:

```bash
docker rm -f web
```

---

## Troubleshooting Commands

Show logs:

```bash
docker logs web
```

Inspect container:

```bash
docker inspect web
```

Execute commands inside container:

```bash
docker exec -it web bash
```

Show port mappings:

```bash
docker port web
```

---

## Volume Commands

List volumes:

```bash
docker volume ls
```

Create volume:

```bash
docker volume create jssba-data
```

Mount volume:

```bash
docker run -it \
  --name volume-test \
  -v jssba-data:/data \
  ubuntu bash
```

---

## Context Commands

List contexts:

```bash
docker context ls
```

Switch context:

```bash
docker context use default
```

---

## Compose Commands

Start stack:

```bash
docker compose up -d
```

Stop stack:

```bash
docker compose down
```

View containers:

```bash
docker compose ps
```

## Network Troublesho*ting

Show listening ports:

```ba*h
ss -tulpn
```

Show a specific p*rt:

```bash
ss -tulpn | grep 8080*```

Show process using a port:

*``bash
sudo lsof -i :8080
```
````*