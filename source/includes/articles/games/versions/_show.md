## <a name="game_versions_show"></a>Get a single game version

> Response body | `HTTP 200`

```JSON
# GET /articles/game_versions/2

{
  "data": {
    "id": "2",
    "type": "game_versions",
    "attributes": {
      "status": "extant",
      "target_fps": null,
      "native_res": null
    },
    "relationships": {
      "game": {
        "data": {
          "id": "47",
          "type": "games"
        },
        "links": {
          "related": "http://localhost:3000/articles/games/dark-souls"
        }
      },
      "platform": {
        "data": {
          "id": "3",
          "type": "platforms"
        },
        "links": {
          "related": "http://localhost:3000/platforms/sony-playstation-3"
        }
      }
    }
  },
  "included": [
    {
      "id": "47",
      "type": "games",
      "attributes": {
        "display_title": "Dark Souls"
      },
      "links": {
        "self": "http://localhost:3000/articles/games/dark-souls"
      }
    },
    {
      "id": "3",
      "type": "platforms",
      "attributes": {
        "name": "PlayStation 3"
      },
      "links": {
        "self": "http://localhost:3000/platforms/sony-playstation-3"
      }
    }
  ],
  "meta": {
    "keywords": "dark souls, playstation 3, platform, version, dbljump, video games, pc games, gaming",
    "description": "Find facts, images and credits for the PlayStation 3 version of Dark Souls at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:19.276Z",
    "updated_at": "2017-04-24T09:09:19.276Z"
  }
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
target_fps | number | | Version target refresh rate. Max 1000.
native_res | string | | Native display resolution, e.g. '720p'. Max 20 chars.

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
