## Get a single media license

> Response body | `HTTP 200`

```JSON
# GET /media/licenses/1

{
    "data": {
        "id": "2",
        "type": "media_licenses",
        "attributes": {
            "name": "Creative Commons Attribution 2.5",
            "short_name": "CC BY 2.5",
            "url": "https://creativecommons.org/licenses/by/2.5/"
        },
        "relationships": {
            "images": {
                "data": [
                    {
                        "id": "39",
                        "type": "images"
                    }
                ]
            },
            "updated_by": {
                "data": null
            },
            "created_by": {
                "data": null
            }
        },
        "links": {
            "self": "http://localhost:3000/media/licenses/2"
        },
        "meta": {
            "created_at": "2017-12-11T11:05:41.010Z",
            "updated_at": "2017-12-11T11:05:41.010Z",
            "meta_description": "Find media published under Creative Commons Attribution 2.5 at Dbljump, the video game reference.",
            "meta_keywords": "Creative Commons Attribution 2.5, CC BY 2.5, creative commons, license, media, dbljump, video games, pc games, gaming",
            "total_images": 1
        }
    }
}
```

Retrieve a single media license.

### HTTP request

`GET /media/licenses/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`
