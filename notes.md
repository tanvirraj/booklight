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

## building api step by step

---

Separate out your API layer from your business logic from your data access layer.

Try to avoid defining huge interfaces alongside their implementations and instead define the interface with the consumer and then you can inject the implementation into the consumer to satisfy the interface you defined.

Don’t overthink it, just go with a structure that makes sense to you. You’re going to end up finding things you want to change about it later anyway, so don’t overthink it.
