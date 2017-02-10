## Sign in a user

> Request body

```JSON
{
 "data": {
	"type": "users",
	"attributes": {
		"email": "tiki@dbljump.com",
		"password": "password"
	}
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "1",
    "type": "users",
    "attributes": {
      "email": "tiki@dbljump.com",
      "username": "tikithekiwi",
      "role": "admin",
      "given_name": "Tiki",
      "family_name": "the Kiwi",
      "gender": "Female",
      "avatar": null,
      "birthday": "1988-09-01",
      "jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoxLCJ1c2VyX3JvbGUiOiJhZG1pbiIsImV4cGlyeSI6IjIwMTctMDItMTEgMTI6MjY6MTUgKzAwMDAifQ.jaAbCFZnyi1Foqf8EktcStZrhmwGIN1Ekw5FFGq622U"
    },
    "relationships": {
      "country": {
        "data": null
      }
    },
    "links": {
      "self": "http://localhost:3000/users/1"
    }
  },
  "meta": {
    "last_signed_in_at": "2017-02-10T12:26:15.891Z",
    "last_sign_in_ip": "::1",
    "sign_in_count": 1,
    "activated_at": "2017-01-28T23:18:37.302Z"
  }
}
```

Sign in an existing user. With valid credentials, returns a JSON web token (JWT) used to authenticate user requests.

* User authentication: not required
* Authorization level: N/A

### HTTP request

`POST /users/authentications`

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
email | string | The user's registered email. Required. Max 255 chars. Must be email format.
password | string | The user's password. Required.

### Success HTTP response code

`200 OK`

### Errors

HTTP code | Error code | Pointer | Title | Detail
--------- | ---------- | ------- | ----- | ------
400 | USER_EMAIL_BLANK | email | Email is required.
401 | USER_CREDENTIALS_INVALID | - | User not authorized. | Invalid email and password combination.
