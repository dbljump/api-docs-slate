## Get media licenses

> Response body | `HTTP 200`

```JSON
# GET /media/licenses?page[size]=2&sort=name

{
    "data": [
        {
            "id": "1",
            "type": "media_licenses",
            "attributes": {
                "name": "A Super License",
                "short_name": "CC BY 2.0",
                "url": "https://creativecommons.org/licenses/by/2.0"
            },
            "relationships": {
                "images": {
                    "data": [
                        {
                            "id": "25",
                            "type": "images"
                        },
                        {
                            "id": "30",
                            "type": "images"
                        },
                        {
                            "id": "34",
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
                "self": "http://localhost:3000/media/licenses/1"
            },
            "meta": {
                "created_at": "2017-12-11T11:05:41.001Z",
                "updated_at": "2017-12-11T16:44:52.176Z",
                "meta_description": "Find media published under A Super License at Dbljump, the video game reference.",
                "meta_keywords": "A Super License, CC BY 2.0, creative commons, license, media, dbljump, video games, pc games, gaming",
                "total_images": 15
            }
        },
        {
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
    ],
    "links": {
        "self": "http://localhost:3000/media/licenses?page%5Bnumber%5D=1&page%5Bsize%5D=2&sort=name",
        "next": "http://localhost:3000/media/licenses?page%5Bnumber%5D=2&page%5Bsize%5D=2&sort=name",
        "last": "http://localhost:3000/media/licenses?page%5Bnumber%5D=6&page%5Bsize%5D=2&sort=name"
    },
    "meta": {
        "total_items": 11
    }
}
```

Retrieve a collection of media licenses. No user authentication required.

### HTTP request

`GET /media/licenses`

### URL query support

Query type | Details
---------- | -------
Filter fields | `name`, `short_name`, `url`
Sort fields | `name`, `short_name`, `url`
Include | `created_by`, `updated_by`
Pagination | Yes
Search | No

### Success HTTP response code

`200 OK`
