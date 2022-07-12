# database
Using docker

```docker
docker run --name auth-psql -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=test -d postgres:14
```


## Initialize database
```bash
docker exec -it auth-psql bash
```

```bash
psql -U admin
```
### Create User table
```sql
create table users(
    id serial not null unique,
    name varchar(64) not null,
    email varchar(64) not null unique,
    password text not null,
    primary key (id)
);
```