## <a name="person_names_create"></a>Create a new person name

> Request body | `POST /articles/people/shigeru-miyamoto/names`

```JSON
{
  "data": {
    "type": "person_names",
    "attributes": {
      "given_names": "Shiggy",
      "family_name": "Shaboo",
      "kind": "nickname",
      "writing_system": "Latin",
      "year_adopted": "1968",
      "dropped": "",
      "year_dropped": "1972"
    },
    "relationships": {
      "place": {
        "data": {
          "id": "102",
          "type": "places"
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
    "id": "63",
    "type": "person_names",
    "attributes": {
      "display_name": "Shiggy Shaboo",
      "given_names": "Shiggy",
      "family_name": "Shaboo",
      "kind": "nickname",
      "writing_system": "Latin",
      "year_adopted": 1968,
      "dropped": true,
      "year_dropped": 1972
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
      "place": {
        "data": {
          "id": "102",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/japan"
        }
      }
    }
  },
  "included": [
    {
      "id": "21",
      "type": "people",
      "attributes": {
        "display_title": "Shigeru Miyamoto"
      },
      "links": {
        "self": "http://localhost:3000/articles/people/shigeru-miyamoto"
      }
    },
    {
      "id": "102",
      "type": "places",
      "attributes": {
        "name": "Japan"
      },
      "links": {
        "self": "http://localhost:3000/places/japan"
      }
    }
  ],
  "meta": {
    "keywords": "shiggy shaboo, shigeru miyamoto, japan, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "Shiggy Shaboo is an alternate name or title for Shigeru Miyamoto. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-05-13T13:08:28.650Z",
    "updated_at": "2017-05-13T13:08:28.650Z"
  }
}
```

Create a new name record for a given person. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/people/{person-slug}/names`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
given_names | string | Y | 1-50 characters.
family_name | string |  | 1-50 characters.
kind | string | Y | The name classification. Must be 'name', 'fullname' or 'nickname'.
writing_system | string | Y | Must be an accepted value.
year_adopted | integer | | Between 1800 and the present year.
dropped | boolean | | True if the name has been dropped. Auto-sets true if `year_dropped` present.
year_dropped | integer | | Between 1800 and the present year.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
place | belongs_to | | places | Can be a country or region.

### Success HTTP response code

`201 Created`
