## Create a new media license

> Request body | `POST /media/licenses`

```JSON
{
  "data": {
    "type": "media_licenses",
    "attributes": {
      "name": "New License",
      "short_name": "New",
      "url": "https://www.licenses.org/new-license"
    }
  }
}
```

> Response body | `HTTP 201`

```JSON
{
    "data": {
        "id": "12",
        "type": "media_licenses",
        "attributes": {
            "name": "New License",
            "short_name": "New",
            "url": "https://www.licenses.org/new-license"
        },
        "relationships": {
            "images": {
                "data": []
            },
            "updated_by": {
                "data": {
                    "id": "2",
                    "type": "users"
                }
            },
            "created_by": {
                "data": {
                    "id": "2",
                    "type": "users"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/media/licenses/12"
        },
        "meta": {
            "created_at": "2017-12-11T20:49:14.349Z",
            "updated_at": "2017-12-11T20:49:14.349Z",
            "meta_description": "Find media published under New License at Dbljump, the video game reference.",
            "meta_keywords": "New License, New, creative commons, license, media, dbljump, video games, pc games, gaming",
            "total_images": 0
        }
    }
}
```

Create a new media license record. The user must be an admin.

### HTTP request

`POST /articles/company_aliases`

### Success HTTP response code

`201 Created`
