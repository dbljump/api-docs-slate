## Sign in a user

> Request body

```JSON
{
 "data": {
  	"type": "users",
  	"attributes": {
  		"email": "neil@example.com",
  		"password": "password",
      "remember_me": "true"
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
        "url": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1703301240.jpg"
      },
      "birthday": "1980-02-14",
      "jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoyLCJ1c2VyX3JvbGUiOiJhZG1pbiIsImV4cGlyeSI6IjIwMTctMDQtMjkgMTI6NTU6MTggKzAwMDAifQ.OL6jcolUQtB-lJy5_d8iisobc_Dqyi35b2Dkxs69lhw"
    },
    "relationships": {
      "country": {
        "data": {
          "id": "219",
          "type": "places"
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
  "included": [
    {
      "id": "219",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "united-kingdom",
        "name": "United Kingdom",
        "short_name": "UK",
        "formatted": "United Kingdom"
      },
      "links": {
        "self": "http://localhost:3000/places/countries/united-kingdom"
      }
    }
  ],
  "meta": {
    "last_signed_in_at": "2017-03-30T12:55:18.073Z",
    "last_sign_in_ip": "86.12.129.15",
    "sign_in_count": 2,
    "activated_at": "2017-03-30T12:40:07.621Z"
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
remember_me | boolean | | JWT authentication token expires in 30 days if `true`, 1 day if `false`. Defaults to `false`.

### Success HTTP response code

`200 OK`

### Response attributes

See the table in [Get single user](#users_show) for all attribute details.

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
jwt | string | Y | The JSON web token used for authentication. Should be added to the HTTP `Authorization` header in further requests until user is signed out.
