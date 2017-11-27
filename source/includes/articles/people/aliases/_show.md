## Get a single person alias

> Response body | `HTTP 200`

```JSON
# GET /articles/person_aliases/41

{
  "data": {
    "id": "41",
    "type": "person_aliases",
    "attributes": {
      "display_text": "岩田 聡",
      "given_names": "聡",
      "family_name": "岩田",
      "kind": "name",
      "writing_system": "Japanese",
      "year_adopted": null,
      "dropped": null,
      "year_dropped": null
    },
    "relationships": {
      "person": {
        "data": {
          "id": "26",
          "type": "people"
        },
        "links": {
          "related": "http://localhost:3000/articles/people/satoru-iwata"
        }
      },
      "place": {
        "data": null
      }
    }
  },
  "included": [
    {
      "id": "26",
      "type": "people",
      "attributes": {
        "display_title": "Satoru Iwata"
      },
      "links": {
        "self": "http://localhost:3000/articles/people/satoru-iwata"
      }
    }
  ],
  "meta": {
    "keywords": "岩田 聡, satoru iwata, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "岩田 聡 is an alternate name or title for Satoru Iwata. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:17.343Z",
    "updated_at": "2017-04-24T09:09:17.343Z"
  }
}
```

Retrieve a single person alias. Person aliases are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/person_aliases/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`

### Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_text | string | Y | The alias.
given_names | string | Y | 1-50 characters.
family_name | string |  | 1-50 characters.
kind | string | Y | The alias classification. Must be 'name', 'fullname' or 'nickname'.
writing_system | string | Y | Must be an accepted value, e.g. 'Latin', 'Japanese' etc.
year_adopted | integer | | Between 1800 and the present year.
dropped | boolean | | True if the alias has been dropped. Auto-sets true if `year_dropped` present.
year_dropped | integer | | Between 1800 and the present year.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
place | places | belongs_to
person | people | belongs_to
