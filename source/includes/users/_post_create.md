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

### Errors

HTTP code | Error code | Pointer
--------- | ---------- | -------
400 | USER_USERNAME_BLANK | username
400 | USER_USERNAME_INVALID | username
400 | USER_USERNAME_TAKEN | username
400 | USER_USERNAME_TOO_SHORT | username
400 | USER_USERNAME_TOO_LONG | username
400 | USER_EMAIL_BLANK | email
400 | USER_EMAIL_INVALID | email
400 | USER_EMAIL_TAKEN | email
400 | USER_EMAIL_TOO_SHORT | email
400 | USER_EMAIL_TOO_LONG | email
400 | USER_PASSWORD_BLANK | password
400 | USER_PASSWORD_TOO_SHORT | password
400 | USER_PASSWORD_TOO_LONG | password
400 | USER_PASSWORD_CONFIRMATION_CONFIRMATION | password_confirmation
