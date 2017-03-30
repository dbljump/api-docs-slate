## Sign in a user

> Request body

```JSON
{
 "data": {
	"type": "users",
	"attributes": {
		"email": "neil@example.com",
		"password": "password"
	}
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "2",
    "type": "users",
    "attributes": {
      "email": "neil@example.com",
      "username": "neil",
      "role": "admin",
      "given_names": "Neil",
      "family_name": "Wheatley",
      "gender": "male",
      "avatar": {
        "url": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1703212334.jpg"
      },
      "birthday": "1980-02-14",
      "jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoyLCJ1c2VyX3JvbGUiOiJhZG1pbiIsImV4cGlyeSI6IjIwMTctMDMtMjIgMjM6NDc6MTQgKzAwMDAifQ.QMT2e25fqh6rEMKWPKojvfYh-WMR-OgUKCyWoLEX-Ms"
    },
    "relationships": {
      "country": {
        "data": {
          "id": "219",
          "type": "place_countries"
        },
        "links": {
          "related": "http://api.dbljump.com/places/countries/united-kingdom"
        }
      },
      "images": {
        "links": {
          "related": "http://api.dbljump.com/users/2/images"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/users/2"
    }
  },
  "meta": {
    "last_signed_in_at": "2017-03-21T23:47:13.936Z",
    "last_sign_in_ip": "94.4.193.77",
    "sign_in_count": 1,
    "activated_at": "2017-03-21T23:34:53.917Z"
  }
}
```

Sign in an existing user. With valid credentials, returns a JSON web token (JWT) used to authenticate user requests.

* User authentication: not required
* Authorization level: N/A

### HTTP request

`POST /users/authentications`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
email | string | Y | The user's registered email. Max 255 chars. Must be email format.
password | string | Y | The user's password.

### Success HTTP response code

`200 OK`
