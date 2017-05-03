## <a name="game_versions_update"></a>Update a game version

> Request body | `PATCH /articles/game_versions/3`

```JSON
{
  "data": {
    "type": "game_versions",
    "id": "3",
    "attributes": {
      "status": "unknown",
      "target_fps": "30",
      "native_res": "1440p"
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
      "target_fps": 30,
      "native_res": "1440p"
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
          "id": "12",
          "type": "platforms"
        },
        "links": {
          "related": "http://localhost:3000/platforms/microsoft-windows-phone"
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
      "id": "12",
      "type": "platforms",
      "attributes": {
        "name": "Windows Phone"
      },
      "links": {
        "self": "http://localhost:3000/platforms/microsoft-windows-phone"
      }
    }
  ],
  "meta": {
    "keywords": "dark souls, windows phone, platform, version, dbljump, video games, pc games, gaming",
    "description": "Find facts, images and credits for the Windows Phone version of Dark Souls at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:19.319Z",
    "updated_at": "2017-05-03T15:57:38.299Z"
  }
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
target_fps | number | | Version target refresh rate. Max 1000.
native_res | string | | Native display resolution, e.g. '720p'. Max 20 chars.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
platform | belongs_to | Y | platforms | Platform this version runs on, e.g. PlayStation 4.

### Success HTTP response code

`200 OK`
