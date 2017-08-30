## <a name="game_titles_show"></a>Get a single game title

> Response body | `HTTP 200`

```JSON
# GET /articles/game_titles/58

{
  "data": {
    "id": "58",
    "type": "game_titles",
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

Retrieve a single game title. Game titles are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/game_titles/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`

### <a name="game_titles_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
title | string | Y | The title.
kind | string | Y | The name classification. Must be 'title', 'working' or 'translated'.
writing_system | string | Y | Must be an accepted value, e.g. 'Latin', 'Japanese' etc.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
place | places | belongs_to
company | companies | belongs_to
version | game_versions | belongs_to

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
