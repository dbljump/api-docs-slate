## Request a password-reset link

> Request body

```JSON
{
  "data": {
    "type": "user_passwords",
    "attributes": {
      "email": "user@example.com"
    }
  }
}
```

A user can request an email with a link to reset their password.

* User authentication: not required
* Authorization level: N/A

### HTTP request

`POST /users/passwords`

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
email | string | The user's registered email. Required. Max 255 chars. Must be email format.

### Success HTTP response code

`204 No Content`

### Errors

HTTP code | Error code | Pointer | Title | Detail
--------- | ---------- | ------- | ----- | ------
400 | USER_EMAIL_INVALID | email | User not found. | Invalid email address.
400 | USER_ACTIVATION_REQUIRED | email | User activation required. | User not yet activated.
