## Get single user

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
      "gender": "Male",
      "avatar": "/uploads/user_avatar/2/1701282319.jpg",
      "birthday": "1980-02-14",
      "jwt": null
    },
    "relationships": {
      "country": {
        "data": {
          "id": "219",
          "type": "place_countries"
        },
        "links": {
          "country": "http://localhost:3000/places/countries/united-kingdom"
        }
      }
    },
    "links": {
      "self": "http://localhost:3000/users/2"
    }
  },
  "meta": {
    "keywords": "neil, neil wheatley, user, dbljump, video games, pc games, gaming",
    "description": "Neil Wheatley is a member at Dbljump, the video game reference.",
    "created_at": "2017-01-28T23:19:21.044Z",
    "updated_at": "2017-02-10T00:41:28.321Z",
    "last_signed_in_at": "2017-02-10T00:41:28.240Z",
    "last_sign_in_ip": "::1",
    "sign_in_count": 4,
    "activated_at": "2017-01-28T23:19:20.476Z"
  }
}
```

Retrieve a single existing user account record. Any user can retrive their own account. An admin-level user can retrieve any user account.

* User authentication: required
* Authorization level: Any, if retrieving own account. Admin if retriveing other user's account.

### HTTP request

`GET /users/'id'` (replace `id` with user record ID)

### Success HTTP response code

`200 OK`

### Errors

HTTP code | Error code | Pointer | Title | Description
--------- | ---------- | ------- | ----- | -----------
401 | USER_LOGIN_EXPIRED | n/a | n/a | The JWT in the header has expired.
401 | USER_UNAUTHORIZED | n/a | n/a | The user doesn't have the right privileges, or there's an authentication problem.
