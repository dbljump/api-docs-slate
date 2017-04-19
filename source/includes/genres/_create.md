## <a name="genres_create"></a>Create a new genre

> Request body | `POST /genres`

```JSON
{
  "data": {
    "type": "genres",
    "attributes": {
      "name": "hog racing",
      "short_name": "hogs",
      "also_known_as": ["alias"]
    },
    "relationships": {
      "parent": {
        "data": {
          "id": "11",
          "type": "genres"
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
    "id": "64",
    "type": "genres",
    "attributes": {
      "name": "hog racing",
      "short_name": "hogs",
      "also_known_as": [
        "alias"
      ],
      "slug": "hog-racing"
    },
    "relationships": {
      "parent": {
        "data": {
          "id": "11",
          "type": "genres"
        },
        "links": {
          "related": "http://api.dbljump.com/genres/racing"
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
      "self": "http://api.dbljump.com/genres/hog-racing"
    }
  },
  "included": [
    {
      "id": "2",
      "type": "users",
      "attributes": {
        "username": "neil",
        "role": "admin",
        "given_names": "Neil",
        "family_name": "W",
        "avatar": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1704170916.jpg"
      },
      "links": {
        "self": "http://api.dbljump.com/users/2"
      }
    }
  ],
  "meta": {
    "keywords": "hog racing, hogs, alias, genre, dbljump, video games, pc games, gaming",
    "description": "Find hog racing-genre games at Dbljump, the video game reference.",
    "created_at": "2017-04-19T11:17:21.829Z",
    "updated_at": "2017-04-19T11:17:21.829Z"
  }
}
```

Create a new genre. User must be an admin.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /genres`

### Request attributes

Attribute values should be lowercase except for proper nouns. For example, 'action' and 'Japanese RPG' are correct; 'Action' is incorrect.

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | Genre name. Unique, up to 50 chars.
short_name | string | | Short name. Unique, up to 10 chars.
also_known_as | array | | Array of alias names, each up to 50 chars.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
parent | belongs_to | | genres | Optional. Must be a top-level genre - no grandparents!

### Success HTTP response code

`201 Created`
