## <a name="company_notes_create"></a>Create a new company note

> Request body | `POST /articles/company_notes`

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
  },
  "relationships": {
    "company": {
      "data": {
        "id": "1",
        "type": "companies"
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
          "type": "users"
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

Create a new company note record. A note is a fact, story or piece of trivia about a company. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/company_notes`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | See [Category](#company_notes_cat).
body | string | Y | The note text. 5-2000 chars.
cite_url | string |  | The URL of the source web page. 5-250 chars.
cite_title | string | | The title of the source web page. 5-250 chars.
cite_website | string | | The name of the source website. 1-100 chars.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
company  | belongs_to  | Y  | companies  | The company the name belongs to.

### <a name="company_notes_cat"></a>Category

The `category` attribute accepts the following values.

Value | Description
---- | -----------
history | Notes related to the history of the company.
organization | Notes related to the structure of the company.
products | Notes related to the company's products.
tech | Notes related to the company's innovations and technologies used.
impact | Notes related to the company's achievements and impact on the wider world.

### Success HTTP response code

`201 Created`
