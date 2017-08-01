## <a name="game_notes_show"></a>Get a single game note

> Response body | `HTTP 200`

```JSON
# GET /articles/game_notes/12

{
  "data": {
    "id": "12",
    "type": "game_notes",
    "attributes": {
      "category": "Development",
      "body": "Was originally intended to feature an all-star cast of Nintendo characters.",
      "cite_url": "https://www.unseen64.net/2014/10/24/wiiu-the-wonderful-101-beta-development",
      "cite_title": "The Wonderful 101 [Beta / Concept – Wii U]",
      "cite_website": "Unseen64"
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
      "version": {
        "data": null,
        "links": {
          "related": "http://localhost:3000/articles/game_versions/2"
        }
      },
      "created_by": {
        "data": {
          "id": "1",
          "type": "created_bies"
        },
        "links": {
          "related": "http://localhost:3000/users/1"
        }
      }
    }
  },
  "meta": {
    "keywords": "the wonderful 101, notes, trivia, facts, dbljump, video games, pc games, gaming",
    "description": "Was originally intended to feature an all-star cast of Nintendo characters.",
    "created_at": "2017-05-17T21:40:11.512Z",
    "updated_at": "2017-05-17T21:40:11.512Z"
  }
}
```

Retrieve a single game note. Game notes are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/game_notes/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`

### <a name="game_notes_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | See [Category](#game_notes_cat).
body | string | Y | The note text. 5-2000 chars.
cite_url | string |  | The URL of the source web page. 5-250 chars.
cite_title | string | | The title of the source web page. 5-250 chars.
cite_website | string | | The name of the source website. 1-100 chars.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
game | games | belongs_to
version | game_versions | belongs_to
created_by | users | belongs_to

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
