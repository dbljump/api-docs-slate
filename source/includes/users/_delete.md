## Delete a user account

Delete an existing user account. A user can delete their own account. An admin can delete any other non-admin account.

* User authentication: required
* Authorization level: Any, if deleting own account. Admin if deleting other user's account. Admin-level accounts can only be deleted by the account owner.

### HTTP request

`DELETE /users/id` (replace `id` with user record ID)

### Success HTTP response code

`204 No Content`


### Errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
401 | USER_LOGIN_EXPIRED | n/a | The JWT in the header has expired.
401 | USER_UNAUTHORIZED | n/a | The user isn't an admin, or there's an authentication problem.
