# Windows - starting postgres in Podman
https://infotechys.com/deploy-postgresql-on-podman/

https://www.geeksforgeeks.org/devops/set-up-a-postgresql-database-with-podman/

## Start Podman
```
podman machine start
```

## Build Pod
```
podman pod create --name postgresql -p 5432:5432
```

## Build a volume for PGDATA
```
podman volume create postgresql-data
```

## Start postgres in the Pod
```
podman run `
--name postgres-db `
--pod postgresql `
-e POSTGRES_DB=mydb `
-e POSTGRES_USER=myuser `
-e POSTGRES_PASSWORD=mypassword `
-v posgresql-data:/var/lib/postgresql/data/ `
postgres
```
