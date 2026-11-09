# Docker Inspect

## Business Problem

As JSSBA Retail Ltd adopts containerized applications, engineers need a reliable method to determine how containers are configured.

When troubleshooting application issues, we need to know:

- Container IP Address
- Container State
- Image Used
- Network Configuration
- Start Time
- Environment Settings

---

## Technical Solution

Docker provides:

```bash
docker inspect
```

This command displays detailed metadata about a container in JSON format.

---

## Commands Executed

Inspect the container:

```bash
docker inspect web
```

---

## Important Fields

### Name

```json
"Name": "/web"
```

Container name.

---

### Image

```json
"Image": "nginx"
```

The image used to create the container.

---

### State

```json
"State": {
    "Status": "running",
    "Running": true
}
```

Shows container status.

---

### IP Address

```json
"IPAddress": "172.17.0.2"
```

Container network address.

---

## Lessons Learned

docker inspect answers:

"What does Docker know about this container?"

Engineers rarely read the entire JSON output.

Instead, they search for specific fields.

---

## Relationship to Kubernetes

Docker:

```bash
docker inspect web
```

Kubernetes equivalent:

```bash
kubectl describe pod <pod-name>
```