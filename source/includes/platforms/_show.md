## <a name="platforms_show"></a>Get single platform

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "31",
    "type": "platforms",
    "attributes": {
      "slug": "sega-32x",
      "name": "32X",
      "short_name": "32X",
      "name_with_holder": "Sega 32X",
      "sphere": "home",
      "kind": "add-on"
    },
    "relationships": {
      "holder": {
        "meta": {}
      },
      "parent": {
        "data": {
          "id": "29",
          "type": "platforms"
        },
        "links": {
          "related": "http://api.dbljump.com/platforms/sega-genesis"
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
      "self": "http://api.dbljump.com/platforms/sega-32x"
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
        "avatar": null
      },
      "links": {
        "self": "http://api.dbljump.com/users/1"
      }
    }
  ],
  "meta": {
    "keywords": "32x, 32x, sega, home, add-on, platform, dbljump, video games, pc games, gaming",
    "description": "Find out about games for 32X by Sega Games Co., Ltd. at Dbljump, the video game reference.",
    "created_at": "2017-03-30T12:40:16.950Z",
    "updated_at": "2017-03-30T12:40:16.950Z"
  }
}
```

Retrieve a single platform record. Platforms are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /platforms/{slug}` (replace `{slug}` with platform record slug)

### Success HTTP response code

`200 OK`

### <a name="platform_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
slug | string | Y | A record ID based on metadata, e.g. 'sega-genesis'.
name | string | Y | The full North American name, or nearest alternative, e.g. 'Genesis'
short_name | string | | The common abbreviated name, e.g. 'SNES'.
name_with_holder | string | | Immutable. A 'full name' including the platform holder name.
sphere | string | Y | The usual platform environment. See [Sphere](#platforms_sphere).
kind | string | Y | Platform type. See [Kind](#platforms_kind).

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
holder | companies | belongs_to
parent | platforms | belongs_to
created_by | users | belongs_to

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
