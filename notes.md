- `cmd/api/` for application-specific code running the server, reading and writing HTTP requests, and managing authentication.

- When httprouter is parsing a request, any interpolated URL parameters will be
  stored in the request context. We can use the ParamsFromContext() function to
  retrieve a slice containing these parameter names and values.
