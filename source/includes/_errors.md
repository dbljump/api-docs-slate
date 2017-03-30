# Errors

General errors not specific to one part of the application.

### Authorization errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
401 | USER_ACTIVATION_REQUIRED | n/a | User not yet activated.
401 | USER_CREDENTIALS_INVALID | n/a | Invalid email and password combination.
401 | USER_LOGIN_EXPIRED | n/a | The JWT in the header has expired.
401 | USER_LOGIN_TOKEN_INVALID | n/a/ | User login token invalid.
401 | USER_UNAUTHORIZED | n/a | User not authorized.

### GET errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
404 | RECORD_NOT_FOUND | n/a | Record not found.
