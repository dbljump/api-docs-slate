## Register a new user

> Request body

```JSON
{
  "data": {
    "type": "users",
    "attributes": {
      "username": "new_user",
      "email": "new@user.com",
      "password": "password",
      "password_confirmation": "password"
    }
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "5",
    "type": "users",
    "attributes": {
      "email": "new@user.com",
      "username": "new_user",
      "role": "member",
      "full_name": "new_user",
      "short_name": "new_user",
      "avatar": {
        "url": null
      }
    },
    "links": {
      "self": "http://localhost:3000/users/5"
    }
  }
}
```

Create a new user account. No authentication is required. Anyone can sign up for a new account with default `role: member`.

* User authentication: not required
* Authorization level: N/A

### HTTP request

`POST /users`

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
username | string | Required. Must be unique. 2-24 chars. Letters, numbers and underscores only.
email | string | Required. Must be unique. Max 255 chars. Email format only. Downcased on save.
password | string | Required. Any 8-24 chars.
password_confirmation | string | Required. Must match password.

### Success HTTP response code

`201`

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
400 | USER_PASSWORD_BLANK | password | Password is required.
400 | USER_PASSWORD_TOO_SHORT | password | Password cannot be less than 8 characters.
400 | USER_PASSWORD_TOO_LONG | password | Password cannot be more than 24 characters.
400 | USER_PASSWORD_CONFIRMATION_CONFIRMATION | password_confirmation | Password and confirmation must match.