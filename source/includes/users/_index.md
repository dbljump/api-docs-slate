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
        "given_names": "Tiki",
        "family_name": "the Kiwi",
        "gender": "Female",
        "avatar": null,
        "birthday": "1988-09-01",
        "jwt": null
      },
      "relationships": {
        "country": {
          "data": null
        },
        "images": {
          "links": {
            "related": "http://api.dbljump.com/users/1/images"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/users/1"
      }
    },
    {
      "id": "3",
      "type": "users",
      "attributes": {
        "email": "member@example.com",
        "username": "member",
        "role": "member",
        "given_names": null,
        "family_name": null,
        "gender": null,
        "avatar": null,
        "birthday": null,
        "jwt": null
      },
      "relationships": {
        "country": {
          "data": null
        },
        "images": {
          "links": {
            "related": "http://api.dbljump.com/users/3/images"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/users/3"
      }
    },
    {
      "id": "4",
      "type": "users",
      "attributes": {
        "email": "editor@example.com",
        "username": "editor",
        "role": "editor",
        "given_names": null,
        "family_name": null,
        "gender": null,
        "avatar": null,
        "birthday": null,
        "jwt": null
      },
      "relationships": {
        "country": {
          "data": null
        },
        "images": {
          "links": {
            "related": "http://api.dbljump.com/users/4/images"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/users/4"
      }
    },
    {
      "id": "2",
      "type": "users",
      "attributes": {
        "email": "neil@example.com",
        "username": "neil",
        "role": "admin",
        "given_names": "Neil",
        "family_name": "Wheatley",
        "gender": "male",
        "avatar": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1703301240.jpg",
        "birthday": "1980-02-14",
        "jwt": null
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
fields[users] | All fields | Return only specified fields, e.g. `/users?fields[users]=username,avatar`
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of users per page

### Success HTTP response code

`200 OK`
