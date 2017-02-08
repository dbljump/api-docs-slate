## Get single user

> HTTP 200 response body

```JSON
```

Retrieve a single existing user account record. Any user can retrive their own account. An admin-level user can retrieve any user account.

* User authentication: required
* Authorization level: Any, if retrieving own account. Admin if retriveing other user's account.

### HTTP request

`GET /users/id` (replace `id` with user record ID)

### Success HTTP response code

`200`

### Errors

HTTP code | Error code | Pointer | Title | Description
--------- | ---------- | ------- | ----- | -----------
401 | USER_LOGIN_EXPIRED | n/a | n/a | The JWT in the header has expired.
401 | USER_UNAUTHORIZED | n/a | n/a | The user doesn't have the right privileges, or there's an authentication problem.
