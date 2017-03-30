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
      "kind": "system",
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
    "id": "27",
    "type": "platforms",
    "attributes": {
      "slug": "nintendo-updated-name",
      "name": "Updated Name",
      "short_name": "Changed",
      "sphere": "portable",
      "kind": "system"
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
          "related": "http://api.dbljump.com/platforms/sony-playstation-2"
        }
      },
      "created_by": {
        "data": {
          "id": "1",
          "type": "users"
        },
        "links": {
          "related": "http://api.dbljump.com/users/1"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/platforms/nintendo-updated-name"
    }
  },
  "included": [
    {
      "id": "1",
      "type": "users",
      "attributes": {
        "username": "tikithekiwi",
        "role": "admin",
        "given_names": "Tiki",
        "family_name": "the Kiwi",
        "avatar": {
          "url": null
        }
      },
      "links": {
        "self": "http://api.dbljump.com/users/1"
      }
    }
  ],
  "meta": {
    "keywords": "updated name, changed, nintendo, portable, system, platform, dbljump, video games, pc games, gaming",
    "description": "Find out about games for Updated Name by Nintendo Co., Ltd. at Dbljump, the video game reference.",
    "created_at": "2017-03-30T12:40:16.756Z",
    "updated_at": "2017-03-30T13:34:53.017Z"
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
