## Get a single game alias

> Response body | `HTTP 200`

```JSON
# GET /articles/game_aliases/58

{
  "data": {
    "id": "58",
    "type": "game_aliases",
    "attributes": {
      "title": "Project P-100",
      "kind": "working",
      "writing_system": "Latin"
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
        "data": null,
        "links": {
          "related": "http://localhost:3000/places/bangladesh"
        }
      },
      "version": {
        "data": null,
        "links": {
          "related": "http://localhost:3000/articles/game_versions/2"
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
    }
  ],
  "meta": {
    "keywords": "project p-100, the wonderful 101, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "Project P-100 is an alternate name or title for The Wonderful 101. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:19.450Z",
    "updated_at": "2017-04-24T09:09:19.450Z"
  }
}
```

Retrieve a single game alias.

### HTTP request

`GET /articles/game_aliases/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`
