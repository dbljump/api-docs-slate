## Update a game alias

> Request body | `PATCH /articles/game_aliases/58`

```JSON
{
  "data": {
    "type": "game_aliases",
    "id": "58",
    "attributes": {
      "title": "アップデート",
      "kind": "title",
      "writing_system": "Japanese"
    },
    "relationships": {
      "place": {
        "data": {
          "id": "102",
          "type": "places"
        }
      },
      "version": {
        "data": {
          "id": "1",
          "type": "game_versions"
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
    "id": "58",
    "type": "game_aliases",
    "attributes": {
      "title": "アップデート",
      "kind": "title",
      "writing_system": "Japanese"
    },
    "relationships": {
      "game": {
        "data": {
          "id": "46",
          "type": "games"
        },
        "links": {
          "related": "http://localhost:3000/articles/games/the-wonderful-101"
        }
      },
      "place": {
        "data": {
          "id": "102",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/japan"
        }
      },
      "version": {
        "data": {
          "id": "1",
          "type": "versions"
        },
        "links": {
          "related": "http://localhost:3000/articles/game_versions/1"
        }
      }
    }
  },
  "included": [
    {
      "id": "46",
      "type": "games",
      "attributes": {
        "display_title": "The Wonderful 101"
      },
      "links": {
        "self": "http://localhost:3000/articles/games/the-wonderful-101"
      }
    },
    {
      "id": "102",
      "type": "places",
      "attributes": {
        "name": "Japan"
      },
      "links": {
        "self": "http://localhost:3000/places/japan"
      }
    }
  ],
  "meta": {
    "keywords": "アップデート, the wonderful 101, japan, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "アップデート is an alternate name or title for The Wonderful 101. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:19.450Z",
    "updated_at": "2017-05-13T12:58:30.190Z"
  }
}
```

Update an existing game alias. The user must be an editor or admin.

### HTTP request

`PATCH /articles/game_aliases/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`
