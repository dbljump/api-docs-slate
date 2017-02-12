## Activate a user account

> Request body

```JSON
{
  "data": {
    "type": "user_activations",
    "attributes": {
      "email": "haggar@user.com",
      "activation_token": "G2MnBqMJVF43tffPmKrmnw"
    }
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "7",
    "type": "users",
    "attributes": {
      "email": "haggar@user.com",
      "username": "haggar",
      "role": "member",
      "given_names": null,
      "family_name": null,
      "gender": null,
      "avatar": null,
      "birthday": null,
      "jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjo3LCJ1c2VyX3JvbGUiOiJtZW1iZXIiLCJleHBpcnkiOiIyMDE3LTAyLTExIDE1OjQ1OjIxICswMDAwIn0.cQcvrTYTumoocdUFFkHNh4uwEIbYU7Ht0z9KRww20wE"
    },
    "relationships": {
      "country": {
        "data": null
      }
    },
    "links": {
      "self": "http://localhost:3000/users/7"
    }
  },
  "meta": {
    "last_signed_in_at": null,
    "last_sign_in_ip": null,
    "sign_in_count": 0,
    "activated_at": "2017-02-10T15:45:21.688Z"
  }
}
```

Activate a user account. This endpoint should be triggered by an activation link sent to the user by email.

* User authentication: not required
* Authorization level: N/A

### HTTP request

`POST /users/activations`

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
email | string | The user's registered email. Provided by the activation link.
activation_token | string | Provided by the activation link.

### Success HTTP response code

`200 OK`

### Errors

HTTP code | Error code | Pointer | Title | Detail
--------- | ---------- | ------- | ----- | ------
400 | USER_ACTIVATION_INVALID | N/A | Cannot activate user. | Invalid user or activation token.
400 | USER_ALREADY_ACTIVATED | email | Cannot activate user. | User already activated.
