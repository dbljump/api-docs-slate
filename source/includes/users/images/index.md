## User images: get all

> HTTP 200 response body

```JSON
# GET /users/1/images

{
    "data": [
        {
            "id": "2",
            "type": "images",
            "attributes": {
                "kind": "photo",
                "slug": "mario-figure-photo",
                "file": "https://dbljumpheroku.s3.amazonaws.com/uploads/images/2/mario-figure.jpg",
                "title": "Mario figure",
                "description": "",
                "year": 2016,
                "date": "2016-07-30",
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
                        "id": "1",
                        "type": "users"
                    },
                    "links": {
                        "related": "http://api.dbljump.com/users/1"
                    }
                },
                "place": {
                    "data": null
                },
                "games": {
                    "data": []
                },
                "companies": {
                    "data": [
                        {
                            "id": "1",
                            "type": "companies"
                        }
                    ]
                },
                "people": {
                    "data": []
                },
                "game_versions": {
                    "data": []
                }
            },
            "links": {
                "self": "http://api.dbljump.com/media/images/mario-figure-photo"
            },
            "meta": {
                "description": "'Mario figure' is a video game image at Dbljump.",
                "keywords": "Mario figure, photo, 2016, 2016-07-30, image, picture, media, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-12T13:30:10.913Z",
                "updated_at": "2017-07-12T13:30:10.913Z"
            }
        },
        {
            "id": "1",
            "type": "images",
            "attributes": {
                "kind": "photo",
                "slug": "nintendo-office-photo",
                "file": "https://dbljumpheroku.s3.amazonaws.com/uploads/images/1/nintendo-hq-kyoto-2006.jpg",
                "title": "Nintendo office",
                "description": "Head Quarters of Nintendo, Minami-ku, Kyoto, Japan. The picture was taken by the poster in February, 2006.",
                "year": 2006,
                "date": "2006-02-18",
                "usage_type": "licensed",
                "usage_license_code": "cc_by_sa_3_0",
                "usage_license_name": "Creative Commons Attribution-ShareAlike 3.0",
                "usage_license_url": "https://creativecommons.org/licenses/by-sa/3.0",
                "attributed_name": "Moja~commonswiki",
                "attributed_url": "",
                "source_url": "https://en.wikipedia.org/wiki/Nintendo#/media/File:Nintendo_office.jpg"
            },
            "relationships": {
                "uploaded_by": {
                    "data": {
                        "id": "1",
                        "type": "users"
                    },
                    "links": {
                        "related": "http://api.dbljump.com/users/1"
                    }
                },
                "place": {
                    "data": null
                },
                "games": {
                    "data": []
                },
                "companies": {
                    "data": [
                        {
                            "id": "1",
                            "type": "companies"
                        }
                    ]
                },
                "people": {
                    "data": []
                },
                "game_versions": {
                    "data": []
                }
            },
            "links": {
                "self": "http://api.dbljump.com/media/images/nintendo-office-photo"
            },
            "meta": {
                "description": "'Nintendo office' is a video game image at Dbljump.",
                "keywords": "Nintendo office, photo, 2006, 2006-02-18, Moja~commonswiki, image, picture, media, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-12T13:30:08.319Z",
                "updated_at": "2017-07-12T13:30:08.319Z"
            }
        }
    ],
    "links": {},
    "meta": {
        "total_items": 2
    }
}
```

Retrieve all images uploaded by the given user. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /users/{user_id}/images` (replace `{user_id}` with country record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[images]=file,title`
filter[{field}] | All records | Filter search by field, e.g. `?filter[kind]=logo`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
