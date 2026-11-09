# Docker Exec

## Business Problem

JSSBA Retail Ltd engineers need a way to enter running containers to investigate:

- Files
- Configuration
- Environment Variables
- Processes
- Logs

---

## Technical Solution

Docker provides:

```bash
docker exec
```

which allows commands to run inside containers.

---

## Commands Executed

Enter container:

```bash
docker exec -it web bash
```

---

## Command Breakdown

### exec

Run a command inside a running container.

### -i

Interactive mode.

### -t

Allocate terminal.

### web

Container name.

### bash

Launch Bash shell.

---

## Observations

Inside the container:

```bash
pwd
```

Output:

```text
/
```

---

Check operating system:

```bash
cat /etc/os-release
```

Output:

```text
Debian GNU/Linux 13
```

---

Check hostname:

```bash
hostname
```

Output:

```text
738c5d7c4ec5
```

---

## Lessons Learned

Containers have:

- Their own filesystem
- Their own hostname
- Their own environment
- Their own processes

Containers are isolated from the host.

---

## Relationship to Kubernetes

Docker:

```bash
docker exec -it web bash
```

Kubernetes:

```bash
kubectl exec -it <pod-name> -- bash
```