### Create Docker Network

```sh
docker network create azure
```

### Create Docker Vote Backend

```sh
docker run -dti --name azure-vote-back -e ALLOW_EMPTY_PASSWORD=yes --net=azure bitnami/redis:6.0.8
```

### Create Docker Container Frontend

```sh
docker run -dti --name azure-vote-front -e REDIS=azure-vote-back --net=azure -p 8081:80 mcr.microsoft.com/azuredocs/azure-vote-front:v1
```

### Check Docker Running

```sh
docker ps
```
