## <a name="games_create"></a>Create a new game

> Request body | `POST /articles/games`

```JSON
{
  "data": {
    "type": "games",
    "attributes": {
      "display_title": "New Game",
      "description": "New Game is an action game developed by some company or other.",
      "release_date": "2015-01-03",
      "release_year": ""
    }
  }
}
```

> Response body | `HTTP 201`

```JSON
{
  "data": {
    "id": "50",
    "type": "games",
    "attributes": {
      "display_title": "New Game",
      "description": "New Game is an action game developed by some company or other.",
      "release_date": "2015-01-03",
      "release_year": 2015,
      "slug": "new-game"
    },
    "relationships": {
      "created_by": {
        "data": {
          "id": "2",
          "type": "users"
        },
        "links": {
          "related": "http://localhost:3000/users/2"
        }
      }
    },
    "links": {
      "self": "http://localhost:3000/articles/games/new-game"
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
        "family_name": "Wheatley",
        "avatar": "http://localhost:3000/uploads/user_avatar/2/1704241009.jpg"
      },
      "links": {
        "self": "http://localhost:3000/users/2"
      }
    }
  ],
  "meta": {
    "keywords": "new game, 2015, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
    "description": "Find New Game trivia, screenshots, credits and other info at Dbljump, the video game reference.",
    "created_at": "2017-04-29T20:07:27.367Z",
    "updated_at": "2017-04-29T20:07:27.367Z"
  }
}
```

Create a new game article. User must be an editor or admin. The genres relationship cannot be edited.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/games`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | 1-250 characters.
description | text | | 1-800 characters.
release_date | date | | Between 1st Jan 1800 and the present.
release_year | integer | | Between 1800 and the present year.

### Success HTTP response code

`201 Created`
