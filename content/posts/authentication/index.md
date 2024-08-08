---
title: "Adding Authentication"
date: 2024-08-05T18:22:09+08:00
draft: true
series: ["Dropbox Clone"]
series_order: 2
---

> TL;DR: I want only authenticated users to be able to use the app, so I'm building an authentication feature

## Context

So for the Dropbox clone, I want to ensure that only verified users are allowed to interact with the API. Hence, I need to build an authentication service to wrap around the APIs I'll be building.

## What needs to be done

For this feature, I need to:

- Create a database for the app
- Create a table for users
- Create an endpoint to register users
- Create an endpoint to login

I've decided to use OAuth, as I don't want to manage our users' credentials. Plus, if I were to go with the email/password route, I'd need to implement password reset and email verification flows. With OAuth, the responsibility of securing and validating the users' credentials falls on the third party.

## The pros and cons of OAuth

### Pros

- It will take less time to develop a solution
- Simplifies the login and registration process
- Offloads credential security to a trusted third party
- Better user experience as they can just use an existing, verified account to access the app

### Cons

- Reliance on a third-party provider
- No control if there are outages
- Access tokens and communication with the third party need to be managed
- If a user has no Google account, they won't be able to access the app

Now that's out of the way, let's build this thing.

## Setting up a database

The simplest way of dealing with this is just using PostgreSQL and connect to it using `sqlx`. The idea for the schema is:

```ts
User {
  id         int
  email      string
  verified   boolean
}
```

As for the database itself, I prefer using Docker Compose, to quickly setup a Postgres service.

This is my `docker-compose.yaml`:

```yaml
version: "3.8"
services:
  postgres_dev:
    image: postgres:13
    ports:
      - 5434:5432
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      POSTGRES_DB: drivebox_dev
    volumes:
      - ./tmp/db:/var/lib/postgresql/data
```

All we have to do here is just run `docker-compose up`. The next thing is to create the table with the schema through migrations.

## Running Migrations

Since we’re using `sqlx`, we can take advantage of their CLI tool to run and manage the migrations.

Install the CLI tool through running `cargo install sqlx-cli`. Then, we need to set an environment variable called `DATABASE_URL` in our terminal, or just create a `.env` file in root of our project. The value should be the connection string to our database.

After that, create a migration file by running `sqlx migrate add <name>` where `<name>` is the action we want to do, e.g: `sqlx migrate add "creating user table"`. This will generate a `.sql` file in a folder called `migrations`.

Add the SQL commands to create a table in the file like below:

```sql
CREATE TABLE IF NOT EXISTS users (
  id integer PRIMARY KEY,
  name varchar,
  email varchar NOT NULL,
  created_at TIMESTAMPTZ NOT NULL,
  updated_at TIMESTAMPTZ NOT NULL,
  verified boolean DEFAULT false

)
```

Once that's done, we run `sqlx migrate run`. Now, we should have a table called `users`.
