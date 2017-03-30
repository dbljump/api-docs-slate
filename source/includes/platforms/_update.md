## <a name="platforms_update"></a>Update a platform record

> Request body

```JSON
{
  "data": {
    "type": "platforms",
    "id": "sega-dreamcast-2",
    "attributes": {
      "name": "Updated Name",
      "short_name": "Changed",
      "sphere": "portable",
      "kind": "console",
      "holder_id": "1",
      "parent_id": "2"
    }
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "50",
    "type": "platforms",
    "attributes": {
      "slug": "sega-updated-name",
      "name": "Updated Name",
      "short_name": "Changed",
      "sphere": "portable",
      "kind": "console"
    },
    "relationships": {
      "holder": {
        "meta": {}
      },
      "parent": {
        "data": {
          "id": "2",
          "type": "platforms"
        },
        "links": {
          "related": "http://api.dbljump.com/platforms/sega-dreamcast"
        }
      },
      "created_by": {
        "data": {
          "id": "2",
          "type": "users"
        },
        "links": {
          "related": "http://api.dbljump.com/users/2"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/platforms/sega-updated-name"
    }
  },
  "meta": {
    "keywords": "updated name, changed, sega, portable, console, platform, dbljump, video games, pc games, gaming",
    "description": "Find out about games for Updated Name by Sega Co., Ltd. at Dbljump, the video game reference.",
    "created_at": "2017-03-24T13:01:13.617Z",
    "updated_at": "2017-03-24T13:01:13.617Z"
  }
}
```

Update an existing platform record. The user must be an admin.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /platforms/{slug}` (replace `{slug}` with platform record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | Max 50 chars. The full North American name, or nearest alternative, e.g. 'Genesis'
short_name | string | | Max 10 chars. The common abbreviated name, e.g. 'SNES'.
sphere | string | Y | The usual platform environment. See [Sphere](#platforms_sphere).
kind | string | Y | Platform type. See [Kind](#platforms_kind).
holder_id | integer | Y | Must be a valid company ID. The platform holder, e.g. 'Sony' for PlayStation.
parent_id | integer | Y | Must be a valid platform ID. Used for add-ons, e.g. 'Sega CD' belongs to Sega Genesis.

### Success HTTP response code

`200 OK`
