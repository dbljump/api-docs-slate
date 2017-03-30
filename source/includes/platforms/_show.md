## <a name="platforms_show"></a>Get single platform

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "1",
    "type": "platforms",
    "attributes": {
      "slug": "sony-playstation",
      "name": "PlayStation",
      "short_name": "PS",
      "sphere": "home",
      "kind": "console"
    },
    "relationships": {
      "holder": {
        "meta": {}
      },
      "parent": {
        "data": null
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
      "self": "http://api.dbljump.com/platforms/sony-playstation"
    }
  },
  "meta": {
    "keywords": "playstation, ps, sony, home, console, platform, dbljump, video games, pc games, gaming",
    "description": "Find out about games for PlayStation by Sony Corporation at Dbljump, the video game reference.",
    "created_at": "2017-03-21T23:35:02.890Z",
    "updated_at": "2017-03-21T23:35:02.890Z"
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
sphere | string | Y | The usual platform environment. See [Sphere](#platforms_sphere).
kind | string | Y | Platform type. See [Kind](#platforms_kind).

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
holder | companies | belongs_to
parent | platforms | belongs_to
created_by | users | belongs_to

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
