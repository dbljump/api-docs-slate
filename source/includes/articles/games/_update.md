## <a name="games_update"></a>Update a game

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
    },
    "relationships": {
      "genres": {
        "data": {
          { "type": "genres", "id": "5" },
          { "type": "genres", "id": "12" }
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
    "id": "46",
    "type": "games",
    "attributes": {
      "display_title": "Changed Name",
      "description": "Updated description for an updated article.",
      "release_date": "1995-11-17",
      "release_year": 1995,
      "slug": "changed-name-69659741-129d-4da5-9a80-98abd30ec586"
    },
    "relationships": {
      "created_by": {
        "data": {
          "id": "1",
          "type": "created_bies"
        },
        "links": {
          "related": "http://localhost:3000/users/1"
        }
      },
      "genres": {
        "data": [
          {
            "id": "5",
            "type": "genres"
          },
          {
            "id": "12",
            "type": "genres"
          }
        ]
      },
      "versions": {
        "data": [
          {
            "id": "1",
            "type": "game_versions"
          }
        ],
        "links": {
          "related": "http://localhost:3000/articles/games/changed-name-69659741-129d-4da5-9a80-98abd30ec586/versions"
        }
      }
    },
    "links": {
      "self": "http://localhost:3000/articles/games/changed-name-69659741-129d-4da5-9a80-98abd30ec586"
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
    },
    {
      "id": "5",
      "type": "genres",
      "attributes": {
        "name": "educational",
        "short_name": ""
      },
      "links": {
        "self": "http://localhost:3000/genres/educational"
      }
    },
    {
      "id": "12",
      "type": "genres",
      "attributes": {
        "name": "role-playing game",
        "short_name": "RPG"
      },
      "links": {
        "self": "http://localhost:3000/genres/role-playing-game"
      }
    }
  ],
  "meta": {
    "keywords": "changed name, 1995, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
    "description": "Find Changed Name trivia, screenshots, credits and other info at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:19.130Z",
    "updated_at": "2017-05-14T21:45:39.016Z"
  }
}
```

Update an existing game article. The user must be an editor. The genres relationship can be edited.

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
