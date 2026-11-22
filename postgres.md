##### POSTGRES container setup
Run container
```
docker run --name my-postgre \
  -e POSTGRES_PASSWORD=mysecretpassword \
  -p 5432:5432 \
  postgres:latest
```

Restart container
```
docker start my-postgre
```

Start psql
```
docker exec -it my-postgre psql -U postgres
```

##### Looking around
List databases
```
\l
```

List tables
```
\dt
```

Get connection info
```
\conninfo
```

Connect to a database
```
\c <db_name>
```


### Data creation
Create database
```
postgres=# create database <db_name>;
CREATE DATABASE
```

Connect to database
```
\c <db_name>
```
