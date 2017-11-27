## Create a new game alias

> Request body | `POST /articles/game_aliases`

```JSON
{
  "data": {
    "type": "game_aliases",
    "attributes": {
      "display_text": "New Title",
      "kind": "title",
      "writing_system": "Latin"
    },
    "relationships": {
      "game": {
        "data": {
          "id": "47",
          "type": "games"
        }
      },
      "place": {
        "data": {
          "id": "17",
          "type": "places"
        }
      },
      "version": {
        "data": {
          "id": "2",
          "type": "game_versions"
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
    "id": "62",
    "type": "game_aliases",
    "attributes": {
      "display_text": "New Title",
      "kind": "title",
      "writing_system": "Latin"
    },
    "relationships": {
      "game": {
        "data": {
          "id": "47",
          "type": "games"
        },
        "links": {
          "related": "http://localhost:3000/articles/games/dark-souls"
        }
      },
      "place": {
        "data": {
          "id": "17",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/bangladesh"
        }
      },
      "version": {
        "data": {
          "id": "2",
          "type": "versions"
        },
        "links": {
          "related": "http://localhost:3000/articles/game_versions/2"
        }
      }
    }
  },
  "included": [
    {
      "id": "47",
      "type": "games",
      "attributes": {
        "display_title": "Dark Souls"
      },
      "links": {
        "self": "http://localhost:3000/articles/games/dark-souls"
      }
    },
    {
      "id": "17",
      "type": "places",
      "attributes": {
        "name": "Bangladesh"
      },
      "links": {
        "self": "http://localhost:3000/places/bangladesh"
      }
    }
  ],
  "meta": {
    "keywords": "new title, dark souls, bangladesh, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "New Title is an alternate name or title for Dark Souls. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-05-13T12:43:38.980Z",
    "updated_at": "2017-05-13T12:43:38.980Z"
  }
}
```

Create a new game alias record. User must be an editor or admin.

### HTTP request

`POST /articles/game_aliases`

### Success HTTP response code

`201 Created`
