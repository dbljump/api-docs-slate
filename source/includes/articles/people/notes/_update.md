## <a name="person_notes_update"></a>Update a person note

> Request body | `PATCH /articles/person_notes/6`

```JSON
{
  "data": {
    "type": "person_notes",
    "id": "6",
    "attributes": {
      "category": "Career",
      "body": "The updated note text.",
      "cite_url": "http://ign.com/updated",
      "cite_title": "The Updated Title",
      "cite_website": "IGN"
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
  "data": {
    "id": "6",
    "type": "person_notes",
    "attributes": {
      "category": "Career",
      "body": "The updated note text.",
      "cite_url": "http://ign.com/updated",
      "cite_title": "The Updated Title",
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
          "id": "1",
          "type": "users"
        },
        "links": {
          "related": "http://localhost:3000/users/1"
        }
      }
    }
  },
  "meta": {
    "keywords": "shigeru miyamoto, notes, trivia, facts, dbljump, video games, pc games, gaming",
    "description": "The updated note text.",
    "created_at": "2017-05-17T21:40:09.742Z",
    "updated_at": "2017-05-18T22:15:04.883Z"
  }
}
```

Update an existing person note. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/person_notes/{id}` (replace `{id}` with record ID)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | See [Category](#person_notes_cat).
body | string | Y | The note text. 5-2000 chars.
cite_url | string |  | The URL of the source web page. 5-250 chars.
cite_title | string | | The title of the source web page. 5-250 chars.
cite_website | string | | The name of the source website. 1-100 chars.

### Success HTTP response code

`200 OK`
