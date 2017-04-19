## <a name="genres_show"></a>Get single genre

> Response body | `HTTP 200`

```JSON
# GET /genres/action

{
  "data": {
    "id": "1",
    "type": "genres",
    "attributes": {
      "name": "action",
      "short_name": "",
      "also_known_as": [],
      "slug": "action"
    },
    "relationships": {
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
      "self": "http://api.dbljump.com/genres/action"
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
    "keywords": "action, genre, dbljump, video games, pc games, gaming",
    "description": "Find action-genre games at Dbljump, the video game reference.",
    "created_at": "2017-04-17T09:17:07.870Z",
    "updated_at": "2017-04-17T09:17:07.870Z"
  }
}
```

Retrieve a single genre record. Genres are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /genres/{slug}` (replace `{slug}` with record slug)

### Success HTTP response code

`200 OK`

### <a name="genre_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | Genre name. Unique, up to 50 chars.
short_name | string | | Short name. Unique, up to 10 chars.
also_known_as | array | | Array of alias names, each up to 50 chars.
slug | string | Y | A record ID based on the name.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
created_by | users | belongs_to
parent | genres | belongs_to

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
