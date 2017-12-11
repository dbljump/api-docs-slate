## Update a media license

> Request body | `PATCH /media/licenses/9`

```JSON
{
  "data": {
    "type": "media_licenses",
    "id": "9",
    "attributes": {
      "name": "Updated License",
      "short_name": "Updated",
      "url": "https://www.licenses.org/updated-license"
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
    "data": {
        "id": "9",
        "type": "media_licenses",
        "attributes": {
            "name": "Updated License",
            "short_name": "Updated",
            "url": "https://www.licenses.org/updated-license"
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
            "self": "http://localhost:3000/media/licenses/9"
        },
        "meta": {
            "created_at": "2017-12-11T11:05:41.084Z",
            "updated_at": "2017-12-11T20:51:21.759Z",
            "meta_description": "Find media published under Updated License at Dbljump, the video game reference.",
            "meta_keywords": "Updated License, Updated, creative commons, license, media, dbljump, video games, pc games, gaming",
            "total_images": 0
        }
    }
}
```

Update an existing media license. The user must be an admin.

### HTTP request

`PATCH /media/licenses/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`
