## <a name="company_notes_create"></a>Create a new company note

> Request body | `POST /articles/companies/nintendo-co-ltd/notes`

```JSON
{
  "data": {
    "type": "company_notes",
    "attributes": {
      "category": "History",
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
    "id": "14",
    "type": "company_notes",
    "attributes": {
      "category": "History",
      "body": "The note text.",
      "cite_url": "http://ign.com/article",
      "cite_title": "The Article Title",
      "cite_website": "IGN"
    },
    "relationships": {
      "company": {
        "data": {
          "id": "1",
          "type": "companies"
        },
        "links": {
          "related": "http://localhost:3000/articles/companies/nintendo-co-ltd"
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
    "keywords": "nintendo co., ltd., notes, trivia, facts, dbljump, video games, pc games, gaming",
    "description": "The note text.",
    "created_at": "2017-05-18T21:42:31.019Z",
    "updated_at": "2017-05-18T21:42:31.019Z"
  }
}
```

Create a new note for a given company. A note is a fact, story or piece of trivia about a company. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/companies/{game-slug}/notes`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | The note category. Must be an accepted value.
body | string | Y | The note text. 5-2000 chars.
cite_url | string |  | The URL of the source web page. 5-250 chars.
cite_title | string | | The title of the source web page. 5-250 chars.
cite_website | string | | The name of the source website. 1-100 chars.

### Success HTTP response code

`201 Created`
