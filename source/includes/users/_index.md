## Get all users

> Response body | `HTTP 200`

```JSON
# GET /users?page[size]=2
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
                    "data": null,
                    "links": {
                        "related": "http://api.dbljump.com/places/united-kingdom"
                    }
                },
                "images": {
                    "links": {
                        "related": "http://api.dbljump.com/users/1/images"
                    }
                }
            },
            "links": {
                "self": "http://api.dbljump.com/users/1"
            },
            "meta": {
                "description": "Tiki the Kiwi is a member at Dbljump, the video game reference.",
                "keywords": "tikithekiwi, Tiki the Kiwi, user, dbljump, video games, pc games, gaming",
                "last_signed_in_at": null,
                "last_sign_in_ip": null,
                "sign_in_count": 0,
                "activated_at": "2017-07-12T13:28:27.875Z",
                "created_at": "2017-07-12T13:28:27.985Z",
                "updated_at": "2017-07-12T13:28:27.985Z"
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
                    "data": null,
                    "links": {
                        "related": "http://api.dbljump.com/places/united-kingdom"
                    }
                },
                "images": {
                    "links": {
                        "related": "http://api.dbljump.com/users/3/images"
                    }
                }
            },
            "links": {
                "self": "http://api.dbljump.com/users/3"
            },
            "meta": {
                "description": "  is a member at Dbljump, the video game reference.",
                "keywords": "member,  , user, dbljump, video games, pc games, gaming",
                "last_signed_in_at": null,
                "last_sign_in_ip": null,
                "sign_in_count": 0,
                "activated_at": "2017-07-12T13:30:04.484Z",
                "created_at": "2017-07-12T13:30:04.561Z",
                "updated_at": "2017-07-12T13:30:04.561Z"
            }
        }
    ],
    "links": {
        "self": "http://api.dbljump.com/users?page%5Bnumber%5D=1&page%5Bsize%5D=2",
        "next": "http://api.dbljump.com/users?page%5Bnumber%5D=2&page%5Bsize%5D=2",
        "last": "http://api.dbljump.com/users?page%5Bnumber%5D=2&page%5Bsize%5D=2"
    },
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
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[users]=username,avatar`
filter[{field}] | All records | Filter search by field, e.g. `?filter[role]=admin`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
