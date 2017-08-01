## <a name="company_notes_show"></a>Get a single company note

> Response body | `HTTP 200`

```JSON
# GET /articles/company_notes/1

{
  "data": {
    "id": "1",
    "type": "company_notes",
    "attributes": {
      "category": "History",
      "body": "Nintendo was a playing card manufacturer before it started making video games.",
      "cite_url": "",
      "cite_title": "",
      "cite_website": ""
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
    "keywords": "nintendo co., ltd., notes, trivia, facts, dbljump, video games, pc games, gaming",
    "description": "Nintendo was a playing card manufacturer before it started making video games.",
    "created_at": "2017-05-17T21:40:00.986Z",
    "updated_at": "2017-05-17T21:40:00.986Z"
  }
}
```

Retrieve a single company note. Game notes are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/company_notes/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`

### <a name="company_notes_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | See [Category](#company_notes_cat).
body | string | Y | The note text. 5-2000 chars.
cite_url | string |  | The URL of the source web page. 5-250 chars.
cite_title | string | | The title of the source web page. 5-250 chars.
cite_website | string | | The name of the source website. 1-100 chars.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
company | companies | belongs_to
created_by | users | belongs_to

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
