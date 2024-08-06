## setup postgresql
```
docker run --name my-postgres --rm -p 5432:5432 -e POSTGRES_PASSWORD=postgres \
    -e PGDATA=/var/lib/postgresql/data/pgdata \
	-v /Users/hspark/workspace/nextjs-dashboard/postgres:/var/lib/postgresql/data \
    -d postgres
 
docker run -it --rm postgres psql -h localhost -U postgres # not work since localhost is in docker space
```

## setup prisma

```
pnpm install prisma --save-dev
npx prisma init --datasource-provider postgresql

DATABASE_URL="postgresql://postgres:postgres@localhost:5432/mydb?schema=app"

\l show db
\dn show schema
\dt show tables
\du show users

```

