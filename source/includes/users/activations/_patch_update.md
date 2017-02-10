## Send a new activation email

> Request body

```JSON
{
  "data": {
    "type": "user_activations",
    "id": "user@email.com"
  }
}

```

Send a new account activation link by email to a user's registered email address.

* User authentication: not required
* Authorization level: N/A

### HTTP request

`PATCH /users/activations/resend`

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
id | string | The user's registered email address.

### Success HTTP response code

`204 No Content`

### Errors

HTTP code | Error code | Pointer | Title | Detail
--------- | ---------- | ------- | ----- | ------
400 | USER_EMAIL_INVALID | email | User not found. | Invalid email address.
400 | USER_ALREADY_ACTIVATED | email | Cannot activate user. | User already activated.
