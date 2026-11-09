# Troubleshooting - MySQL Container Failed

## Business Problem

JSSBA Retail Ltd requires a MySQL database container.

Container creation appeared successful but the service was not running.

---

## Symptoms

Command:

```bash
docker run -d --name jtest mysql
```

Container exited immediately.

Check status:

```bash
docker ps -a
```

Output:

```text
Exited (1)
```

---

## Investigation

View logs:

```bash
docker logs jtest
```

Output:

```text
Database is uninitialized and password option is not specified
```

---

## Root Cause

MySQL requires one of:

```text
MYSQL_ROOT_PASSWORD
MYSQL_ALLOW_EMPTY_PASSWORD
MYSQL_RANDOM_ROOT_PASSWORD
```

during initialization.

---

## Resolution

Example:

```bash
docker run -d \
  --name mysql-db \
  -e MYSQL_ROOT_PASSWORD=Secret123 \
  mysql
```

---

## Lesson Learned

Always inspect logs when a container exits unexpectedly.

Useful commands:

```bash
docker ps -a
docker logs <container>
```