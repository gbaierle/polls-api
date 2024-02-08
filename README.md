# Polls API

This project implements a simplified Rest API to create polls and handle votes.

The polls, options and votes are persisted in a Postgres database. In addition, a Redis instance is used to store the polls voting, so there is no need to perform a `count(*)` in the database to get the results, which could be expensive as the voting results grow.

Also, a websocket connection is used to message the subscribers of a poll with the real-time results.

Tech stack used: **Node.js**, **Typescript**, **Fastify**, **Prisma ORM**, **Docker**, **Postgres**, **Redis**.

## Setup steps

- Install dependencies
```bash
npm install
```

- Generate `.env` file
```bash
cp .env.example .env
```

- Setup Docker database and Redis
```bash
docker-compose up -d
```


- Run migrations
```bash
npx prisma migrate
```

- Start server
```bash
npm run dev
```
