# Troubleshooting - Docker Context Issue

## Symptoms

Commands:

```bash
docker version
docker ps
```

returned:

```text
Failed to initialize: protocol not available
```

---

## Investigation

Check contexts:

```bash
docker context ls
```

Current context:

```text
desktop-linux
```

---

## Root Cause

Docker CLI was using a context incompatible with the current WSL setup.

---

## Resolution

Switch back:

```bash
docker context use default
```

Verify:

```bash
docker version
```

Expected:

```text
Client:
Server:
```

---

## Lesson Learned

When Docker behaves unexpectedly check:

```bash
docker context ls
docker version
docker ps
```