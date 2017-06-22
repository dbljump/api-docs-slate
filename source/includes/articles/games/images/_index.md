## Get all game images

> Response body | `HTTP 200`

```JSON
# GET /articles/games/pong/images

{
    "data": [
        {
            "id": "6",
            "type": "images",
            "attributes": {
                "kind": "poster",
                "slug": "pong-poster-poster",
                "file": "http://localhost:3000/uploads/images/6/file.gif",
                "title": "Pong poster",
                "description": "Promotional poster for Pong.",
                "year": 1981,
                "date": null,
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
                    "data": null,
                    "links": {
                        "related": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
                    }
                },
                "games": {
                    "data": [
                        {
                            "id": "45",
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
                    "data": []
                }
            },
            "links": {
                "self": "http://localhost:3000/media/images/pong-poster-poster"
            }
        }
    ],
    "links": {},
    "meta": {
        "total_items": 1
    }
}
```

Retrieve all images associated with a given game article. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{game-id}/images` (replace `game-id` with the game ID or slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[images]=file,title`
filter[{field}] | All records | Filter search by field, e.g. `?filter[kind]=logo`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
