## <a name="game_versions_update"></a>Update a game version

> Request body | `PATCH /articles/game_versions/3`

```JSON
{
  "data": {
    "type": "game_versions",
    "id": "3",
    "attributes": {
      "status": "unknown",
      "fps_target": "30",
      "fps_unlocked": "false",
      "res_w": "1920",
      "res_h": "1080",
      "res_unlocked": "false"
    },
    "relationships": {
      "platform": {
        "data": {
          "id": "12",
          "type": "platforms"
        }
      }
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
    "data": {
        "id": "3",
        "type": "game_versions",
        "attributes": {
            "status": "unknown",
            "fps_target": 30,
            "fps_unlocked": false,
            "res_w": 1920,
            "res_h": 1080,
            "res_unlocked": false
        },
        "relationships": {
            "game": {
                "data": {
                    "id": "95",
                    "type": "games"
                },
                "links": {
                    "related": "http://localhost:3000/articles/games/shadow-of-the-beast"
                }
            },
            "platform": {
                "data": {
                    "id": "12",
                    "type": "platforms"
                },
                "links": {
                    "related": "http://localhost:3000/platforms/sony-playstation-2"
                }
            },
            "primary_image": {
                "data": null
            },
            "images": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/game_versions/3/images"
                }
            }
        },
        "meta": {
            "description": "Find facts, images and credits for the PlayStation 2 version of Shadow of the Beast at Dbljump, the video game reference.",
            "keywords": "Shadow of the Beast, PlayStation 2, platform, version, dbljump, video games, pc games, gaming",
            "created_at": "2017-07-27T22:24:39.018Z",
            "updated_at": "2017-07-30T21:24:04.585Z"
        }
    },
    "included": [
        {
            "id": "95",
            "type": "games",
            "attributes": {
                "display_title": "Shadow of the Beast"
            },
            "links": {
                "self": "http://localhost:3000/articles/games/shadow-of-the-beast"
            },
            "meta": {
                "description": "Find Shadow of the Beast trivia, screenshots, credits and other info at Dbljump, the video game reference.",
                "keywords": "Shadow of the Beast, 1989, Amiga, Atari ST, Commodore 64, Amstrad CPC, ZX Spectrum, Genesis, Master System, Lynx, FM Towns, TurboGrafx-CD, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-27T22:24:38.945Z",
                "updated_at": "2017-07-27T22:25:24.453Z"
            }
        },
        {
            "id": "12",
            "type": "platforms",
            "attributes": {
                "name": "PlayStation 2"
            },
            "links": {
                "self": "http://localhost:3000/platforms/sony-playstation-2"
            },
            "meta": {
                "description": "Find out about games for PlayStation 2 by Sony Corporation at Dbljump, the video game reference.",
                "keywords": "PlayStation 2, PS2, Sony, home, system, platform, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-27T22:24:36.464Z",
                "updated_at": "2017-07-27T22:24:36.464Z"
            }
        }
    ]
}
```

Update an existing game version. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/game_versions/{id}` (replace `{id}` with record ID)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
status | string | Y | Must be 'extant', 'rumored', 'canceled' or 'unknown'.
fps_target | number | | Version target refresh rate. Max 1000.
fps_unlocked | boolean | | True if framerate is dynamic based on hardware (usually for modern PC games).
res_w | number | | Native display resolution width, e.g. '720'. Max 10,000.
res_h | number | | Native display resolution height, e.g. '1280'. Max 10,000.
res_unlocked | boolean | | True if resolution is dynamic based on hardware (usually for modern PC games).

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
platform | belongs_to | Y | platforms | Platform this version runs on, e.g. PlayStation 4.

### Success HTTP response code

`200 OK`
