## Get all users

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "1",
      "type": "users",
      "attributes": {
        "email": "tiki@dbljump.com",
        "username": "tikithekiwi",
        "role": "admin",
        "given_name": "Tiki",
        "family_name": "the Kiwi",
        "full_name": "Tiki the Kiwi",
        "short_name": "Tiki",
        "gender": "Female",
        "avatar": {
          "url": null
        },
        "jwt": null
      },
      "links": {
        "self": "http://localhost:3000/users/1"
      }
    },
    {
      "id": "3",
      "type": "users",
      "attributes": {
        "email": "member@example.com",
        "username": "member",
        "role": "member",
        "given_name": null,
        "family_name": null,
        "full_name": "member",
        "short_name": "member",
        "gender": null,
        "avatar": {
          "url": null
        },
        "jwt": null
      },
      "links": {
        "self": "http://localhost:3000/users/3"
      }
    },
    {
      "id": "4",
      "type": "users",
      "attributes": {
        "email": "editor@example.com",
        "username": "editor",
        "role": "editor",
        "given_name": null,
        "family_name": null,
        "full_name": "editor",
        "short_name": "editor",
        "gender": null,
        "avatar": {
          "url": null
        },
        "jwt": null
      },
      "links": {
        "self": "http://localhost:3000/users/4"
      }
    },
    {
      "id": "2",
      "type": "users",
      "attributes": {
        "email": "neil@example.com",
        "username": "neil",
        "role": "admin",
        "given_name": "Neil",
        "family_name": "Wheatley",
        "full_name": "Neil Wheatley",
        "short_name": "Neil",
        "gender": "Male",
        "avatar": {
          "url": "/uploads/user_avatar/2/1701282319.jpg"
        },
        "jwt": null
      },
      "links": {
        "self": "http://localhost:3000/users/2",
        "avatar": "http://localhost:3000/uploads/user_avatar/2/1701282319.jpg"
      }
    }
  ],
  "links": {},
  "meta": {
    "total_items": 4
  }
}
```

Retrieve all users. Automatically paginated. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`GET /users`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of users per page

### Errors

HTTP code | Error code | Pointer | Title | Description
--------- | ---------- | ------- | ----- | -----------
401 | USER_LOGIN_EXPIRED | n/a | n/a | The JWT in the header has expired.
401 | USER_UNAUTHORIZED | n/a | n/a | The user isn't an admin, or there's an authentication problem.
