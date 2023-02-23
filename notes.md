- `cmd/api/` for application-specific code running the server, reading and writing HTTP requests, and managing authentication.

- When httprouter is parsing a request, any interpolated URL parameters will be
  stored in the request context. We can use the ParamsFromContext() function to
  retrieve a slice containing these parameter names and values.

- when parse request , we also create a `readJSON` helper to decode json request to map struct and add error message for bad reqeust. in `readJSON` helper
