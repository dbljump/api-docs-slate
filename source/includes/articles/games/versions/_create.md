## <a name="game_versions_create"></a>Create a new game version

> Request body | `POST /articles/games/dark-souls/versions`

```JSON
{
  "data": {
    "type": "game_versions",
    "attributes": {
      "status": "rumored",
      "target_fps": "60",
      "native_res": "1080p"
    },
    "relationships": {
      "platform": {
        "data": {
          "id": "13",
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
    "id": "5",
    "type": "game_versions",
    "attributes": {
      "status": "rumored",
      "target_fps": 60,
      "native_res": "1080p"
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
          "id": "13",
          "type": "platforms"
        },
        "links": {
          "related": "http://localhost:3000/platforms/nintendo-switch"
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
      "id": "13",
      "type": "platforms",
      "attributes": {
        "name": "Switch"
      },
      "links": {
        "self": "http://localhost:3000/platforms/nintendo-switch"
      }
    }
  ],
  "meta": {
    "keywords": "dark souls, switch, platform, version, dbljump, video games, pc games, gaming",
    "description": "Find facts, images and credits for the Switch version of Dark Souls at Dbljump, the video game reference.",
    "created_at": "2017-05-03T15:52:55.575Z",
    "updated_at": "2017-05-03T15:52:55.575Z"
  }
}
```

Create a new game version. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/games/{game-slug}/versions` (replace `{game-slug}` with game slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
status | string | Y | Must be 'extant', 'rumored', 'canceled' or 'unknown'.
target_fps | number | | Version target refresh rate. Max 1000.
native_res | string | | Native display resolution, e.g. '720p'. Max 20 chars.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
platform | belongs_to | Y | platforms | Platform this version runs on, e.g. PlayStation 4.

### Success HTTP response code

`201 Created`
