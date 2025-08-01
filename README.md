# postgres-playground
Learning about [PostgreSQL](https://www.postgresql.org/about/)!

## PostgreSQL Server
A PostgreSQL server is needed because it’s the database engine that stores, manages, and processes the actual database. Without it, there's no database to connect to or run queries on. 

You can spin up a server using any of the following.

#### PostgreSQL CLI
This option requires you to download PostgreSQL and its binaries onto your local machine. 

```
psql -U postgres
```

#### Docker
This option is great to keep things isolated and you won't need to download PostgreSQL or `psql` on your local machine. _It requires Docker though!_

```
docker run -e POSTGRES_USER=myusername -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -d postgres
docker stop postgres
docker start postgres
```

## Clients
Now that you have a server running, if you want to interact with it, you'll need a client. A client lets you send SQL commands, view outputs, and manage the database. Without a client, you have no way to talk to the server directly.

You can interact with the server using any of the following.

#### PostgreSQL CLI
Just like using [`psql`](https://www.postgresql.org/docs/current/app-psql.html) to spin up the server, it can also be used as a client to interact with the server too.
```
psql -h localhost -U postgres
```

#### GUI
But sometimes I prefer a graphical visualization better! You can use the included [pgAdmin](https://www.pgadmin.org/) GUI tool from when you first downloaded PostgreSQL. 

Or, I like to use the [DBeaver](https://dbeaver.io/) GUI tool since it includes interactions with other RDBMS and NoSQL databases. It's also free, open-source, and the GUI is intuitive (at least to me)!
