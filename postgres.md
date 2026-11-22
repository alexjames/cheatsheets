##### POSTGRES container setup
Run container
```
docker run --name my-postgre \
  -e POSTGRES_PASSWORD=mysecretpassword \
  -p 5432:5432 \
  postgres:latest
```

Start psql
```
docker exec -it my-postgre psql -U postgres
```

##### Looking around

