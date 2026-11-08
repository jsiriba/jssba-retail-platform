# Docker Networking

Every container receives its own network stack.

Example:

```bash
hostname -i
```

Output:

```text
172.17.0.2
```

This is the container IP address.

---

## Port Publishing

Syntax:

```bash
docker run -p HOST_PORT:CONTAINER_PORT
```

Example:

```bash
docker run -d \
  --name web \
  -p 8095:80 \
  nginx
```

Meaning:

```text
Host Port 8095
      ↓
Container Port 80
```

Verify mapping:

```bash
docker port web
```

Output:

```text
80/tcp -> 0.0.0.0:8095
```

---

## Important Lesson

Container ports are not automatically accessible from the host.

Ports must be explicitly published.