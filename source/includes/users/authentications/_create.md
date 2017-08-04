## Sign in a user

> Request body | `POST /users//authentications`

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
            "avatar": "null",
            "avatar_thumb": null,
            "birthday": "1980-02-14",
            "jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoyLCJ1c2VyX3JvbGUiOiJhZG1pbiIsImV4cGlyeSI6IjIwMTctMDgtMTEgMTM6NDg6NDcgKzAwMDAifQ.Q8HJ0HNUDnKc776MAT4S-c7OqVtB20Uq8yQTxt_twqY"
        },
        "relationships": {
            "country": {
                "data": {
                    "id": "219",
                    "type": "places"
                },
                "links": {
                    "related": "http://api.dbljump.com/places/united-kingdom"
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
        },
        "meta": {
            "description": "Neil Wheatley is a member at Dbljump, the video game reference.",
            "keywords": "neil, Neil Wheatley, user, dbljump, video games, pc games, gaming",
            "last_signed_in_at": "2017-07-12T13:48:47.195Z",
            "last_sign_in_ip": "86.12.129.15",
            "sign_in_count": 2,
            "activated_at": "2017-07-12T13:30:02.955Z",
            "created_at": "2017-07-12T13:30:03.831Z",
            "updated_at": "2017-07-12T13:48:47.255Z"
        }
    },
    "included": [
        {
            "id": "219",
            "type": "places",
            "attributes": {
                "name": "United Kingdom"
            },
            "links": {
                "self": "http://api.dbljump.com/places/united-kingdom"
            },
            "meta": {
                "description": "Find video game companies and games industry professionals from United Kingdom at Dbljump.",
                "keywords": "United Kingdom, UK, GB, British, country, place, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-12T13:28:33.305Z",
                "updated_at": "2017-07-12T13:28:33.305Z"
            }
        }
    ]
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
