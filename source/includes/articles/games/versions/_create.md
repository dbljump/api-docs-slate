## <a name="game_versions_create"></a>Create a new game version

> Request body | `POST /articles/game_versions`

```JSON
{
  "data": {
    "type": "game_versions",
    "attributes": {
      "status": "rumored",
      "fps_target": "60",
      "fps_unlocked": "false",
      "res_w": "1920",
      "res_h": "1080",
      "res_unlocked": "false"
    },
    "relationships": {
      "game": {
          "data": {
              "id": "79",
              "type": "games"
          }
        }
      },
      "platform": {
        "data": {
          "id": "60",
          "type": "platforms"
        }
      }
    }
  }
}
```

> Response body | `HTTP 201`

```JSON
{
    "data": {
        "id": "96",
        "type": "game_versions",
        "attributes": {
            "status": "rumored",
            "fps_target": 60,
            "fps_unlocked": false,
            "res_w": 1920,
            "res_h": 1080,
            "res_unlocked": false
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
                    "id": "60",
                    "type": "platforms"
                },
                "links": {
                    "related": "http://localhost:3000/platforms/commodore-international-commodore-64"
                }
            },
            "primary_image": {
                "data": null
            },
            "images": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/game_versions/96/images"
                }
            }
        },
        "meta": {
            "description": "Find facts, images and credits for the Commodore 64 version of Dark Souls at Dbljump, the video game reference.",
            "keywords": "Dark Souls, Commodore 64, platform, version, dbljump, video games, pc games, gaming",
            "created_at": "2017-07-30T21:21:34.021Z",
            "updated_at": "2017-07-30T21:21:34.021Z"
        }
    },
    "included": [
        {
            "id": "79",
            "type": "games",
            "attributes": {
                "display_title": "Dark Souls"
            },
            "links": {
                "self": "http://localhost:3000/articles/games/dark-souls"
            },
            "meta": {
                "description": "Find Dark Souls trivia, screenshots, credits and other info at Dbljump, the video game reference.",
                "keywords": "Dark Souls, 2011, PlayStation 3, Xbox 360, Windows, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-27T22:24:38.585Z",
                "updated_at": "2017-07-27T22:25:00.050Z"
            }
        },
        {
            "id": "60",
            "type": "platforms",
            "attributes": {
                "name": "Commodore 64"
            },
            "links": {
                "self": "http://localhost:3000/platforms/commodore-international-commodore-64"
            },
            "meta": {
                "description": "Find out about games for Commodore 64 by Commodore International at Dbljump, the video game reference.",
                "keywords": "Commodore 64, C64, Commodore International, home, system, platform, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-27T22:24:37.796Z",
                "updated_at": "2017-07-27T22:24:37.796Z"
            }
        }
    ]
}
```

Create a new game version. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/game_versions`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
status | string | Y | Must be 'extant', 'rumored', 'canceled' or 'unknown'.
fps_target | number | | Version target refresh rate. Max 1000.
fps_unlocked | boolean | | True if framerate is dynamic based on hardware (usually for modern PC games)
res_w | number | | Native display resolution width, e.g. '720'. Max 10,000.
res_h | number | | Native display resolution height, e.g. '1280'. Max 10,000.
res_unlocked | boolean | | True if resolution is dynamic based on hardware (usually for modern PC games)

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
game  | belongs_to  | Y  | games  | The game the version belongs to.
platform | belongs_to | Y | platforms | Platform this version runs on, e.g. PlayStation 4.

### Success HTTP response code

`201 Created`
