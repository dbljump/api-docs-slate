## Send a new activation email

> Request body | `POST /users/activations`

```JSON
{
  "data": {
    "type": "user_activations",
    "attributes": {
      "email": "user@example.com"
    }
  }
}

```

Send a new account activation link by email to a user's registered email address.

* User authentication: not required
* Authorization level: N/A

### HTTP request

`POST /users/activations`

### Request attributes

Attribute | Type | Req'd | Description
--------- | ---- | ----- | -----------
email | string | The user's registered email address.

### Success HTTP response code

`204 No Content`

### Errors

Errors specific to user activation link requests.

HTTP code | Error code | Pointer | Title | Detail
--------- | ---------- | ------- | ----- | ------
400 | USER_EMAIL_INVALID | email | User not found. | Invalid email address.
400 | USER_ALREADY_ACTIVATED | email | Cannot activate user. | User already activated.
