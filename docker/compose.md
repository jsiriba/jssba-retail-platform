# Docker Compose

Docker Compose allows multiple containers to be defined as code.

## Example

compose.yml

```yaml
services:
  web:
    image: nginx
    container_name: compose-web

    ports:
      - "8096:80"

    restart: unless-stopped
```

Start services:

```bash
docker compose up -d
```

Stop services:

```bash
docker compose down
```

---

## Benefits

- Infrastructure as Code
- Repeatable environments
- Easier management of multi-container applications