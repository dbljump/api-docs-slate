## Update a user account details

> Request body

```JSON
{
  "data": {
    "type": "users",
    "id": 5,
    "attributes": {
      "username": "updated_username",
      "email": "updated@user.com",
      "role": "editor",
      "password": "newpassword",
      "password_confirmation": "newpassword"
    }
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "type": "users",
    "id": "5",
    "attributes": {
      "username": "updated_username",
      "email": "updated@user.com",
      "role": "editor"
    },
    "links": {
      "self": "http://localhost:3000/users/5"
    }
  }
}
```

Update an existing user account. A user can update their own account. An admin can update any other non-admin account.

Admin-level authorization is required to update attributes role.

* User authentication: required
* Authorization level: Any if editing own account. Admin if editing other user's account. Admin-level accounts can only be edited by the account owner.

### HTTP request

`PATCH /users/id` (replace `id` with user record ID)

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
username | string | Required. Must be unique. 2-24 chars. Letters, numbers and underscores only.
email | string | Required. Must be unique. Max 255 chars. Email format only. Downcased on save.
role | string | Authorization level. Must be 'member', 'editor' or 'admin'. Can only be updated by admin users.
password | string | New password. Any 8-24 chars.
password_confirmation | string | Required if changing password. Must match password.

### Success HTTP response code

`200`

### Errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | USER_USERNAME_BLANK | username | Username is required.
400 | USER_USERNAME_INVALID | username | Username can only contain letters, numbers, and underscores.
400 | USER_USERNAME_TAKEN | username | Username has already been taken.
400 | USER_USERNAME_TOO_SHORT | username | Username cannot be less than 2 characters.
400 | USER_USERNAME_TOO_LONG | username | Username cannot be more than 24 characters.
400 | USER_EMAIL_BLANK | email | Email is required.
400 | USER_EMAIL_INVALID | email | Email must be a valid address.
400 | USER_EMAIL_TAKEN | email | Email has already been taken.
400 | USER_EMAIL_TOO_LONG | email | Username cannot be more than 255 characters.
400 | USER_ROLE_INVALID | role | Role must be 'member', 'editor', or 'admin'.
400 | USER_PASSWORD_BLANK | password | Password is required.
400 | USER_PASSWORD_TOO_SHORT | password | Password cannot be less than 8 characters.
400 | USER_PASSWORD_TOO_LONG | password | Password cannot be more than 24 characters.
400 | USER_PASSWORD_CONFIRMATION_CONFIRMATION | password_confirmation | Password and confirmation must match.
401 | USER_LOGIN_EXPIRED | n/a | The JWT in the header has expired.
401 | USER_UNAUTHORIZED | n/a | The user isn't an admin, or there's an authentication problem.
