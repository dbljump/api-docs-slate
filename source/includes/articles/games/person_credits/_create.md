## <a name="game_person_credits_create"></a>Create a game person-credit

> Request body | `POST /articles/games/dark-souls/notes`

```JSON
{
  "data": {
    "type": "game_notes",
    "attributes": {
      "category": "Development",
      "body": "The note text.",
      "cite_url": "http://ign.com/article",
      "cite_title": "The Article Title",
      "cite_website": "IGN"
    },
    "relationships": {
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
    "id": "13",
    "type": "game_notes",
    "attributes": {
      "category": "Development",
      "body": "The note text.",
      "cite_url": "http://ign.com/article",
      "cite_title": "The Article Title",
      "cite_website": "IGN"
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
      "version": {
        "data": {
          "id": "2",
          "type": "versions"
        },
        "links": {
          "related": "http://localhost:3000/articles/game_versions/2"
        }
      },
      "created_by": {
        "data": {
          "id": "2",
          "type": "users"
        },
        "links": {
          "related": "http://localhost:3000/users/2"
        }
      }
    }
  },
  "meta": {
    "keywords": "dark souls, notes, trivia, facts, dbljump, video games, pc games, gaming",
    "description": "The note text.",
    "created_at": "2017-05-17T21:44:11.984Z",
    "updated_at": "2017-05-17T21:44:11.984Z"
  }
}
```

Create a new note for a given game. A note is a fact, story or piece of trivia about a game. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/games/{game-slug}/notes`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | The note category. Must be an accepted value.
body | string | Y | The note text. 5-2000 chars.
cite_url | string |  | The URL of the source web page. 5-250 chars.
cite_title | string | | The title of the source web page. 5-250 chars.
cite_website | string | | The name of the source website. 1-100 chars.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
version | belongs_to | | game_versions | Version must belong to same game as note.

### Success HTTP response code

`201 Created`
