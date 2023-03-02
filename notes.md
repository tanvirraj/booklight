- `cmd/api/` for application-specific code running the server, reading and writing HTTP requests, and managing authentication.

- When httprouter is parsing a request, any interpolated URL parameters will be
  stored in the request context. We can use the ParamsFromContext() function to
  retrieve a slice containing these parameter names and values.

- when parse request , we also create a `readJSON` helper to decode json request to map struct and add error message for bad reqeust. in `readJSON` helper

---

## c-05-database-setup-config:

- create db from psql
- install pg db driver
- add db dsn in zsh like this
  `echo 'export BOOKLIGHT_DB_DSN=postgres://booklight:password@localhost/booklight?sslmode=disable' >> ~/.zshrc`

---

- we’re going to wrap our MovieModel in a parent Models struct. Doing this is totally optional, but it has the benefit of giving you a convenient single ‘container’ which can hold and represent all your database models as your application grows.

## building api step by step

- setup router
- add router handler function to handle request and response
- create db
- create table with migrations
- create model

---

Separate out your API layer from your business logic from your data access layer.

Try to avoid defining huge interfaces alongside their implementations and instead define the interface with the consumer and then you can inject the implementation into the consumer to satisfy the interface you defined.

Don’t overthink it, just go with a structure that makes sense to you. You’re going to end up finding things you want to change about it later anyway, so don’t overthink it.
