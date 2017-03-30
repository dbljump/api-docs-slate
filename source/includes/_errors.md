# Errors

General errors not specific to one part of the application.

### Authorization errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
401 | USER_LOGIN_EXPIRED | n/a | The JWT in the header has expired.
401 | USER_UNAUTHORIZED | n/a | The user doesn't have the right permissions, or there's an authentication problem.

### GET errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
404 | RECORD_NOT_FOUND | n/a | Record not found.
