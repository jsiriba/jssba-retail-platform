# Troubleshooting - Port Conflict On 8080

## Symptoms

Nginx container was started using:

```bash
docker run -d \
  --name web \
  -p 8080:80 \
  nginx
```

Browser displayed a Tomcat page instead of the Nginx welcome page.

---

## Investigation

Verify running containers:

```bash
docker ps
```

Verify nginx content:

```bash
docker exec -it web bash

cat /usr/share/nginx/html/index.html
```

Investigate host services.

---

## Root Cause

Port 8080 was already in use by a Tomcat service outside Docker.

---

## Resolution

Use a different host port:

```bash
docker rm -f web

docker run -d \
  --name web \
  -p 8095:80 \
  nginx
```

---

## Verification

Check mapping:

```bash
docker port web
```

Output:

```text
80/tcp -> 0.0.0.0:8095
```

Access:

```text
http://localhost:8095
```

---

## Lesson Learned

Always verify port availability before publishing container ports.

### Check Existing Docker Port Usage

View currently published Docker ports:

```bash
docker ps
```

Example:

```text
0.0.0.0:8095->80/tcp
```

This indicates host port 8095 is already in use by a container.

---

### Check Listening Ports On Linux

View listening ports:

```bash
ss -tulpn
```

Example:

```bash
ss -tulpn | grep 8080
```

Output:

```text
LISTEN 0 128 *:8080
```

This indicates*a service is already listening on *ort 808*.

---

### Alternative

```bash
s*do*lsof -i :8080
```

*xample Output:

```text
COMMAND*  PID   USER
java     1234 *tomcat
```

This identifies*the process using the port.

---

*## Troubleshooting Workflow*
Before publishing a port*

```bash
docker ps

ss -tulpn*| grep <port>

sudo lsof*-i :<port>
```

Always verify port availability in the correct operating system.

For WSL/Linux
ss -tulpn

For Windows
Open PowerShell:
netstat -ano    lists all running process
netstat -ano | findstr :8080
or
Get-NetTCPConnection -LocalPort 8080

---

### Exam*le

Bad:

```bash*docker*run -d \
  --name web \
  -p 8080*80 \
  nginx
```

when Tom*at is already using:

```text
8080*```

Good:

*``bash
docker run -d \
  --name we* \
  -* 8095:80 \
  nginx
```

---

*## JSSBA Retail Lesson

*s JSSBA Retail grows and*hosts:

- Nginx
-*Tomcat
- Grafana
- Prometheus
- AW*

*ort planning becomes important.

T*o services cannot listen on the sa*e host port simultaneously.



## WSL Networking Lesson

A port conflict may originate from Windows and not from WSL.

Verify Linux listeners:

```bash
ss -tulpn | grep <port>

netstat -ano | findstr :<port>