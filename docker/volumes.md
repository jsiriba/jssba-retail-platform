# Docker Volumes

Volumes provide persistent storage outside containers.

## Why Volumes Exist

Containers are temporary.

Deleting a container can remove data stored inside it.

Volumes preserve data independently of containers.

---

## Create Volume

```bash
docker volume create jssba-data
```

List volumes:

```bash
docker volume ls
```

---

## Mount A Volume

```bash
docker run -it \
    --name volume-test \
    -v jssba-data:/data \
    ubuntu bash
```

Inside container:

```bash
echo "JSSBA Retail" > /data/company.txt
```

---

## Persistence Test

Delete container:

```bash
docker rm volume-test
```

Create another container:

```bash
docker run -it \
    --name volume-test-2 \
    -v jssba-data:/data \
    ubuntu bash
```

Verify:

```bash
cat /data/company.txt
```

Output:

```text
JSSBA Retail
```

The file persists even though the original container was deleted.

---

## Key Concept

Container ≠ Data

Volume = Data