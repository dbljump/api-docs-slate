## <a name="company_notes_update"></a>Update a company note

> Request body | `PATCH /articles/company_notes/1`

```JSON
{
  "data": {
    "type": "company_notes",
    "id": "1",
    "attributes": {
      "category": "History",
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
    "id": "1",
    "type": "company_notes",
    "attributes": {
      "category": "History",
      "body": "The updated note text.",
      "cite_url": "http://ign.com/updated",
      "cite_title": "The Updated Title",
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
    "description": "The updated note text.",
    "created_at": "2017-05-17T21:40:00.986Z",
    "updated_at": "2017-05-18T21:55:39.825Z"
  }
}
```

Update an existing company note. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/company_notes/{id}` (replace `{id}` with record ID)

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
version | belongs_to | | company_versions | Version must belong to same company as title.

### Success HTTP response code

`200 OK`
