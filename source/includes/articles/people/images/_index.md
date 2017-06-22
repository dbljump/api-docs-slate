## Get all person images

> Response body | `HTTP 200`

```JSON
# GET /articles/people/shigeru-miyamoto/images

{
    "data": [
        {
            "id": "7",
            "type": "images",
            "attributes": {
                "kind": "photo",
                "slug": "portrait-of-shigeru-miyamoto-photo",
                "file": "http://localhost:3000/uploads/images/7/file.gif",
                "title": "Portrait of Shigeru Miyamoto",
                "description": "Shigeru Miyamoto in Kyoto on 12 April 2012.",
                "year": 2012,
                "date": "2012-04-12",
                "usage_type": "free",
                "usage_license_code": null,
                "usage_license_name": null,
                "usage_license_url": null,
                "attributed_name": null,
                "attributed_url": null,
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
                    "data": {
                        "id": "2932",
                        "type": "places"
                    },
                    "links": {
                        "related": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
                    }
                },
                "games": {
                    "data": []
                },
                "companies": {
                    "data": []
                },
                "people": {
                    "data": [
                        {
                            "id": "21",
                            "type": "people"
                        }
                    ]
                },
                "game_versions": {
                    "data": []
                }
            },
            "links": {
                "self": "http://localhost:3000/media/images/portrait-of-shigeru-miyamoto-photo"
            }
        }
    ],
    "links": {},
    "meta": {
        "total_items": 1
    }
}
```

Retrieve all images associated with a given person article. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/people/{person-id}/images` (replace `person-id` with the person ID or slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[images]=file,title`
filter[{field}] | All records | Filter search by field, e.g. `?filter[kind]=logo`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
