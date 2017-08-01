## <a name="person_notes_create"></a>Create a new person note

> Request body | `POST /articles/people/shigeru-miyamoto/notes`

```JSON
{
  "data": {
    "type": "person_notes",
    "attributes": {
      "category": "Career",
      "body": "The note text.",
      "cite_url": "http://ign.com/article",
      "cite_title": "The Article Title",
      "cite_website": "IGN"
    }
  }
}
```

> Response body | `HTTP 201`

```JSON
{
  "data": {
    "id": "15",
    "type": "person_notes",
    "attributes": {
      "category": "Career",
      "body": "The note text.",
      "cite_url": "http://ign.com/article",
      "cite_title": "The Article Title",
      "cite_website": "IGN"
    },
    "relationships": {
      "person": {
        "data": {
          "id": "21",
          "type": "people"
        },
        "links": {
          "related": "http://localhost:3000/articles/people/shigeru-miyamoto"
        }
      },
      "created_by": {
        "data": {
          "id": "2",
          "type": "created_bies"
        },
        "links": {
          "related": "http://localhost:3000/users/2"
        }
      }
    }
  },
  "meta": {
    "keywords": "shigeru miyamoto, notes, trivia, facts, dbljump, video games, pc games, gaming",
    "description": "The note text.",
    "created_at": "2017-05-18T22:09:16.930Z",
    "updated_at": "2017-05-18T22:09:16.930Z"
  }
}
```

Create a new note for a given person. A note is a fact, story or piece of trivia about a person. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/people/{game-slug}/notes`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | See [Category](#person_notes_cat).
body | string | Y | The note text. 5-2000 chars.
cite_url | string |  | The URL of the source web page. 5-250 chars.
cite_title | string | | The title of the source web page. 5-250 chars.
cite_website | string | | The name of the source website. 1-100 chars.

### <a name="person_notes_cat"></a>Category

The `category` attribute accepts the following values.

Value | Description
----- | -----------
bio | Notes related to the person's personal life or biography.
education | Notes related to the person's education and academic achievements.
career | Notes related to the person's professional life and achievements.
impact | Notes related to the person's impact on the wider world.

### Success HTTP response code

`201 Created`
