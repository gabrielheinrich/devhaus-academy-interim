# Fastify

## pg Setup

```ts
import { Client } from "pg";

const db = new Client({
  user: "spark",
  database: "spark",
  password: "spark",
  host: "localhost",
  port: 5432,
});

async function main() {
  await db.connect();
  const response = await db.query("SELECT * FROM notes");
  return response.rows;
}

main();
```

## Fastify Setup

```ts
import fastify from "fastify";

const app = fastify({ logger: true });

async function main() {
  await app.listen(3000);
}

main();
```

## Fastify request / reply objects

```ts
app.get("/inspect-fastify/:id", async (request, reply) => {
  console.log("Method", request.method); // GET POST PUT UPDATE DELETE
  console.log("URL", request.url);
  console.log("Query", request.query);
  console.log("Params", request.params);
  console.log("Body", request.body);
  console.log("Headers", request.headers);

  reply.status(418); // I am a teapot

  reply.header("my-custom-header", "This is a custom header");

  return {
    message: "This is my response body",
  };
});
```

## Recipe: Developing an API route

1. Create an example insomnia request
2. Setup the route handler and return fake data
3. Goto pgadmin to Construct and Debug SQL Query
4. Inside handler execute SQL query against database
5. Send the rows back to the user

```ts
app.get("/notes", async (request, reply) => {
  const response = await db.query("SELECT * FROM notes");
  return response.rows;
});
```

## Checklist: Connecting a REST Server to its Database

1. Make sure docker container of postgres is running: docker ps
2. Log into pgadmin to see if the database and tables are setup
3. Make sure the server starts without an error (i.e. db.connect works)
4. Execute an HTTP request with insomnia on a route that does a query
