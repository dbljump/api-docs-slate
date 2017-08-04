## Activate a user account

> Request body | `PATCH /users/activations/{activation_token}`

```JSON
{
  "data": {
    "type": "user_activations",
    "id": "G2MnBqMJVF43tffPmKrmnw",
    "attributes": {
      "email": "user@example.com"
    }
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "5",
    "type": "users",
    "attributes": {
      "email": "user@example.com",
      "username": "new_user",
      "role": "member",
      "given_names": null,
      "family_name": null,
      "gender": null,
      "avatar": null,
      "avatar_thumb": null,
      "birthday": null,
      "jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjo1LCJ1c2VyX3JvbGUiOiJtZW1iZXIiLCJleHBpcnkiOiIyMDE3LTAzLTIyIDIzOjU1OjMyICswMDAwIn0.WqLjZkgyEh3Trv2U9q2PDBkbY4toWPJx02zbqTSn540"
    },
    "relationships": {
      "country": {
        "data": {
          "id": "5",
          "type": "places"
        },,
        "links": {
          "related": "http://api.dbljump.com/places/countries/andorra"
        }
      },
      "images": {
        "links": {
          "related": "http://api.dbljump.com/users/5/images"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/users/5"
    },
    "meta": {
      "last_signed_in_at": null,
      "last_sign_in_ip": null,
      "sign_in_count": 0,
      "activated_at": "2017-03-21T23:55:32.873Z"
    }
  },
  "included": [
  {
    "id": "5",
    "type": "places",
    "attributes": {
      "subtype": "countries",
      "slug": "andorra",
      "name": "Andorra",
      "short_name": null,
      "formatted": "Andorra"
    },
    "links": {
      "self": "http://localhost:3000/places/countries/united-kingdom"
    }
  }
]
}
```

Activate a user account. This endpoint should be triggered by an activation link sent to the user by email. The response includes a JWT authentication token, which can be used to automatically sign in the user.

* User authentication: not required
* Authorization level: N/A

### HTTP request

`PATCH /users/activations/{activation_token}` (replace `{activation_token}` with the user's activation token)

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
id | string | User activation token. Provided in the activation link.
email | string | The user's registered email. Provided in the activation link.

### Success HTTP response code

`200 OK`

### Response attributes

See the table in [Get single user](#users_show) for all attribute details.

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
jwt | string | Y | The JSON web token used for authentication. Should be added to the HTTP `Authorization` header in further requests until user is signed out.

### Errors

Errors specific to user activations.

HTTP code | Error code | Pointer | Title | Detail
--------- | ---------- | ------- | ----- | ------
400 | USER_ACTIVATION_INVALID | N/A | Cannot activate user. | Invalid user or activation token.
400 | USER_ALREADY_ACTIVATED | email | Cannot activate user. | User already activated.
