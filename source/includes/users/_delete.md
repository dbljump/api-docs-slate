## Delete a user account

Delete an existing user account. A user can delete their own account. An admin can delete any other non-admin account.

* User authentication: required
* Authorization level: Any, if deleting own account. Admin if deleting other user's account. Admin-level accounts can only be deleted by the account owner.

### HTTP request

`DELETE /users/{id}` (replace `{id}` with user record ID)

### Success HTTP response code

`204 No Content`
