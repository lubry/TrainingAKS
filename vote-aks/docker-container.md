### Create Docker Network

```sh
docker network create votenet
```

### Create Docker Vote Backend

```sh
docker run -dti --name azure-vote-back -e ALLOW_EMPTY_PASSWORD=yes --net=votenet bitnami/redis:6.0.8
```

### Create Docker Container Frontend

```sh
docker run -dti --name azure-vote-front -e REDIS=azure-vote-back --net=votenet -p 8081:80 mcr.microsoft.com/azuredocs/azure-vote-front:v1
```

### Check Docker Running

```sh
docker ps
```
