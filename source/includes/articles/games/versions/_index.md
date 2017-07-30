## Get all game versions

> Response body | `HTTP 200`

```JSON
# GET /articles/games/dark-souls/versions?page[size]=2

{
    "data": [
        {
            "id": "83",
            "type": "game_versions",
            "attributes": {
                "status": "extant",
                "fps_target": 30,
                "fps_unlocked": null,
                "res_w": 1280,
                "res_h": 720,
                "res_unlocked": null
            },
            "relationships": {
                "game": {
                    "data": {
                        "id": "79",
                        "type": "games"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/games/dark-souls"
                    }
                },
                "platform": {
                    "data": {
                        "id": "13",
                        "type": "platforms"
                    },
                    "links": {
                        "related": "http://localhost:3000/platforms/sony-playstation-3"
                    }
                },
                "primary_image": {
                    "data": null
                },
                "images": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/game_versions/83/images"
                    }
                }
            },
            "meta": {
                "description": "Find facts, images and credits for the PlayStation 3 version of Dark Souls at Dbljump, the video game reference.",
                "keywords": "Dark Souls, PlayStation 3, platform, version, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-27T22:24:39.631Z",
                "updated_at": "2017-07-27T22:24:39.631Z"
            }
        },
        {
            "id": "84",
            "type": "game_versions",
            "attributes": {
                "status": "extant",
                "fps_target": 30,
                "fps_unlocked": null,
                "res_w": 1280,
                "res_h": 720,
                "res_unlocked": null
            },
            "relationships": {
                "game": {
                    "data": {
                        "id": "79",
                        "type": "games"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/games/dark-souls"
                    }
                },
                "platform": {
                    "data": {
                        "id": "18",
                        "type": "platforms"
                    },
                    "links": {
                        "related": "http://localhost:3000/platforms/microsoft-xbox-360"
                    }
                },
                "primary_image": {
                    "data": null
                },
                "images": {
                    "data": [],
                    "links": {
                        "related": "http://localhost:3000/articles/game_versions/84/images"
                    }
                }
            },
            "meta": {
                "description": "Find facts, images and credits for the Xbox 360 version of Dark Souls at Dbljump, the video game reference.",
                "keywords": "Dark Souls, Xbox 360, platform, version, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-27T22:24:39.641Z",
                "updated_at": "2017-07-27T22:24:39.641Z"
            }
        }
    ],
    "links": {
        "self": "http://localhost:3000/articles/games/dark-souls/versions?page%5Bnumber%5D=1&page%5Bsize%5D=2",
        "next": "http://localhost:3000/articles/games/dark-souls/versions?page%5Bnumber%5D=2&page%5Bsize%5D=2",
        "last": "http://localhost:3000/articles/games/dark-souls/versions?page%5Bnumber%5D=2&page%5Bsize%5D=2"
    },
    "meta": {
        "total_items": 3
    }
}
```

Retrieve all game versions. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{game-slug}/versions`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[game_versions]=status,fps_target`
filter[{field}] | All records | Filter search by field, e.g. `?filter[status]=rumored`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
