## <a name="games_update"></a>Update a company

> Request body | `PATCH /articles/games/pong`

```JSON
{
  "data": {
    "type": "games",
    "id": "pong",
    "attributes": {
      "display_title": "Changed Name",
      "description": "Updated description for an updated article.",
      "release_date": "1995-11-17",
      "release_year": ""
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
  "data": {
    "id": "45",
    "type": "games",
    "attributes": {
      "display_title": "Changed Name",
      "description": "Updated description for an updated article.",
      "release_date": "1995-11-17",
      "release_year": 1995,
      "slug": "changed-name-72d6b822-372c-4f99-93b5-98d17ac0acf1"
    },
    "relationships": {
      "created_by": {
        "data": {
          "id": "1",
          "type": "users"
        },
        "links": {
          "related": "http://localhost:3000/users/1"
        }
      }
    },
    "links": {
      "self": "http://localhost:3000/articles/games/changed-name-72d6b822-372c-4f99-93b5-98d17ac0acf1"
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
        "self": "http://localhost:3000/users/1"
      }
    }
  ],
  "meta": {
    "keywords": "changed name, 1995, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
    "description": "Find Changed Name trivia, screenshots, credits and other info at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:19.087Z",
    "updated_at": "2017-04-29T20:10:31.175Z"
  }
}
```

Update an existing game article. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/games/{slug}` (replace `{slug}` with record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | 1-250 characters.
description | text | | 1-800 characters.
release_date | date | | Between 1st Jan 1800 and the present.
release_year | integer | | Between 1800 and the present year.

### Success HTTP response code

`200 OK`
