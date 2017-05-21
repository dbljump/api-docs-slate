## <a name="genres_update"></a>Update a genre record

> Request body | `PATCH /genres/action`

```JSON
{
  "data": {
    "type": "genres",
    "id": "action",
    "attributes": {
      "name": "updated name",
      "short_name": "updated",
      "also_known_as": ["aka"]
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
  "data": {
    "id": "1",
    "type": "genres",
    "attributes": {
      "name": "updated name",
      "short_name": "updated",
      "also_known_as": [
        "aka"
      ],
      "slug": "updated-name"
    },
    "relationships": {
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
      "self": "http://api.dbljump.com/genres/updated-name"
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
    "keywords": "updated name, updated, aka, genre, dbljump, video games, pc games, gaming",
    "description": "Find updated name-genre games at Dbljump, the video game reference.",
    "created_at": "2017-04-17T09:17:07.870Z",
    "updated_at": "2017-04-19T11:22:21.345Z"
  }
}
```

Update an existing genre record. The user must be an admin.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /genres/{slug}` (replace `{slug}` with record slug)

### Request attributes

Attribute values should be lowercase except for proper nouns. For example, 'action' and 'Japanese RPG' are correct; 'Action' is incorrect.

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | Genre name. Unique, up to 50 chars.
short_name | string | | Short name. Unique, up to 10 chars.
also_known_as | array | | Array of alias names, each up to 50 chars.

### Success HTTP response code

`200 OK`
