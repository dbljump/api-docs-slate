## Get all game version images

> Response body | `HTTP 200`

```JSON
# GET /articles/game_versions/1/images

{
    "data": [
        {
            "id": "3",
            "type": "images",
            "attributes": {
                "kind": "screen",
                "slug": "the-wonderful-101-title-screen-wii-u-screen",
                "file": "http://localhost:3000/uploads/images/3/file.gif",
                "title": "The Wonderful 101 title screen (Wii U)",
                "description": "Title screen from The Wonderful 101 on Wii U",
                "year": 2013,
                "date": "2013-09-12",
                "usage_type": "fair",
                "usage_license_code": null,
                "usage_license_name": null,
                "usage_license_url": null,
                "attributed_name": "",
                "attributed_url": "",
                "source_url": ""
            },
            "relationships": {
                "uploaded_by": {
                    "data": {
                        "id": "2",
                        "type": "users"
                    },
                    "links": {
                        "related": "http://localhost:3000/users/2"
                    }
                },
                "place": {
                    "data": null
                },
                "games": {
                    "data": [
                        {
                            "id": "46",
                            "type": "games"
                        }
                    ]
                },
                "companies": {
                    "data": []
                },
                "people": {
                    "data": []
                },
                "game_versions": {
                    "data": [
                        {
                            "id": "1",
                            "type": "game_versions"
                        }
                    ]
                }
            },
            "links": {
                "self": "http://localhost:3000/media/images/the-wonderful-101-title-screen-wii-u-screen"
            }
        }
    ],
    "links": {},
    "meta": {
        "total_items": 1
    }
}
```

Retrieve all images associated with a given game version. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/game_versions/{version-id}/images` (replace `version-id` with the version ID)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[images]=file,title`
filter[{field}] | All records | Filter search by field, e.g. `?filter[kind]=logo`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
