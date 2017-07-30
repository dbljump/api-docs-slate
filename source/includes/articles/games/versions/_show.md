## <a name="game_versions_show"></a>Get a single game version

> Response body | `HTTP 200`

```JSON
# GET /articles/game_versions/80

{
    "data": {
        "id": "80",
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
                    "id": "82",
                    "type": "games"
                },
                "links": {
                    "related": "http://localhost:3000/articles/games/the-legend-of-zelda-breath-of-the-wild"
                }
            },
            "platform": {
                "data": {
                    "id": "25",
                    "type": "platforms"
                },
                "links": {
                    "related": "http://localhost:3000/platforms/nintendo-wii-u"
                }
            },
            "primary_image": {
                "data": null
            },
            "images": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/game_versions/80/images"
                }
            }
        },
        "meta": {
            "description": "Find facts, images and credits for the Wii U version of The Legend of Zelda: Breath of the Wild at Dbljump, the video game reference.",
            "keywords": "The Legend of Zelda: Breath of the Wild, Wii U, platform, version, dbljump, video games, pc games, gaming",
            "created_at": "2017-07-27T22:24:39.603Z",
            "updated_at": "2017-07-27T22:24:39.603Z"
        }
    },
    "included": [
        {
            "id": "82",
            "type": "games",
            "attributes": {
                "display_title": "The Legend of Zelda: Breath of the Wild"
            },
            "links": {
                "self": "http://localhost:3000/articles/games/the-legend-of-zelda-breath-of-the-wild"
            },
            "meta": {
                "description": "Find The Legend of Zelda: Breath of the Wild trivia, screenshots, credits and other info at Dbljump, the video game reference.",
                "keywords": "The Legend of Zelda: Breath of the Wild, 2017, Switch, Wii U, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-27T22:24:38.651Z",
                "updated_at": "2017-07-27T22:25:04.144Z"
            }
        },
        {
            "id": "25",
            "type": "platforms",
            "attributes": {
                "name": "Wii U"
            },
            "links": {
                "self": "http://localhost:3000/platforms/nintendo-wii-u"
            },
            "meta": {
                "description": "Find out about games for Wii U by Nintendo Co., Ltd. at Dbljump, the video game reference.",
                "keywords": "Wii U, WiiU, Nintendo, home, system, platform, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-27T22:24:36.910Z",
                "updated_at": "2017-07-27T22:24:36.910Z"
            }
        }
    ]
}
```

Retrieve a single game version. Game versions are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/game_versions/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`

### <a name="game_version_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
status | string | Y | Must be 'extant', 'rumored', 'canceled' or 'unknown'.
fps_target | number | | Version target refresh rate. Max 1000.
fps_unlocked | boolean | | True if framerate is dynamic based on hardware (usually for modern PC games).
res_w | number | | Native display resolution width, e.g. '720'. Max 10,000.
res_h | number | | Native display resolution height, e.g. '1280'. Max 10,000.
res_unlocked | boolean | | True if resolution is dynamic based on hardware (usually for modern PC games).

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
game | games | belongs_to
platform | platforms | belongs_to

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
games | game | display_title
platforms | platform | name

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
