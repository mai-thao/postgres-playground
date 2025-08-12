# postgres-playground
Learning about [PostgreSQL](https://www.postgresql.org/about/)!

## PostgreSQL Server
A PostgreSQL server is needed because it’s the database engine that stores, manages, and processes the actual database. Without it, there's no database to connect to or run queries on. 

You can spin up a server using any of the following.

### PostgreSQL CLI
This option requires you to download PostgreSQL and its binaries onto your local machine. 

```
psql -U postgres
```

### Docker
This option is great to keep things isolated and you won't need to download PostgreSQL or `psql` on your local machine. _It requires Docker though!_

```
docker run -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -d postgres
docker stop postgres
docker start postgres
```

#### Common Issues
* When starting the docker container, only the `POSTGRES_PASSWORD` environmental variable needs to be set. It will use the default `postgres` for username and database name
    * BUT! If you want to set your own username and database name:
    
      `docker run -e POSTGRES_USER=myuser -e POSTGRES_PASSWORD=mysecretpassword -e POSTGRES_DB=mycooldb -p 5432:5432 -d postgres`
* You might run into an issue where port 5432 is used by another process (e.g. a native PostgreSQL server installed on Windows). Use the commands: `netstat -aon | findstr :5432` and `tasklist /FI "PID eq <PASTE_PID_HERE>"` to find out!

## Clients
Now that you have a server running, if you want to interact with it, you'll need a client. A client lets you send SQL commands, view outputs, and manage the database. Without a client, you have no way to talk to the server directly.

You can interact with the server using any of the following.

### PostgreSQL CLI
Just like using [`psql`](https://www.postgresql.org/docs/current/app-psql.html) to spin up the server, it can also be used as a client to interact with the server too.
```
psql -h localhost -U postgres
```

### GUI
But sometimes I prefer a graphical visualization better! You can use the included [pgAdmin](https://www.pgadmin.org/) GUI tool from when you first downloaded PostgreSQL. 

Or, I like to use the [DBeaver](https://dbeaver.io/) GUI tool since it includes interactions with other RDBMS and NoSQL databases. It's also free, open-source, and the GUI is intuitive (at least to me)!
  * Build the Postgres connection using the following URL: `jdbc:postgresql://localhost:5432/postgres`
