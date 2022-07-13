# Database
Using docker

```docker
docker run --name auth-psql -p 5432:5432 -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=test -e POSTGRES_DBNAME=admin -d postgres:14
```

```bash
docker exec -it auth-psql bash
```

```bash
psql -U admin
```

```sql
create table users(
    id serial not null unique,
    name varchar(64) not null,
    email varchar(64) not null unique,
    password text not null,
    primary key (id)
);
```


# UI

Install Node.js and follow the instructions in its `Readme.md` file