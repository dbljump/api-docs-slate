## <a name="person_notes_show"></a>Get a single person note

> Response body | `HTTP 200`

```JSON
# GET /articles/person_notes/6

{
  "data": {
    "id": "6",
    "type": "person_notes",
    "attributes": {
      "category": "Education",
      "body": "Studied industrial design at Kanazawa Municipal College of Industrial Arts.",
      "cite_url": "",
      "cite_title": "",
      "cite_website": ""
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
    "description": "Studied industrial design at Kanazawa Municipal College of Industrial Arts.",
    "created_at": "2017-05-17T21:40:09.742Z",
    "updated_at": "2017-05-17T21:40:09.742Z"
  }
}
```

Retrieve a single person note. Game notes are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/person_notes/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`

### <a name="person_notes_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | See [Category](#person_notes_cat).
body | string | Y | The note text. 5-2000 chars.
cite_url | string |  | The URL of the source web page. 5-250 chars.
cite_title | string | | The title of the source web page. 5-250 chars.
cite_website | string | | The name of the source website. 1-100 chars.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
person | people | belongs_to
created_by | users | belongs_to

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
