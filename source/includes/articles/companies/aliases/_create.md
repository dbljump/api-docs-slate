## Create a new company alias

> Request body | `POST /articles/company_aliases`

```JSON
{
  "data": {
    "type": "company_aliases",
    "attributes": {
      "display_text": "New Name",
      "kind": "name",
      "writing_system": "Latin",
      "year_adopted": "2010",
      "dropped": "",
      "year_dropped": "2017"
    },
    "relationships": {
      "company": {
        "data": {
          "id": "1",
          "type": "companies"
        }
      },
      "place": {
        "data": {
          "id": "17",
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
    "id": "61",
    "type": "company_aliases",
    "attributes": {
      "display_text": "New Name",
      "kind": "name",
      "writing_system": "Latin",
      "year_adopted": 2010,
      "dropped": true,
      "year_dropped": 2017
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
      "place": {
        "data": {
          "id": "17",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/bangladesh"
        }
      }
    }
  },
  "included": [
    {
      "id": "1",
      "type": "companies",
      "attributes": {
        "display_title": "Nintendo Co., Ltd."
      },
      "links": {
        "self": "http://localhost:3000/articles/companies/nintendo-co-ltd"
      }
    },
    {
      "id": "17",
      "type": "places",
      "attributes": {
        "name": "Bangladesh",
        "formatted": "Bangladesh"
      },
      "links": {
        "self": "http://localhost:3000/places/bangladesh"
      }
    }
  ],
  "meta": {
    "keywords": "new name, nintendo co., ltd., bangladesh, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "New Name is an alternate name or title for Nintendo Co., Ltd.. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-05-03T10:05:55.948Z",
    "updated_at": "2017-05-03T10:05:55.948Z"
  }
}
```

Create a new company alias record. User must be an editor or admin.

### HTTP request

`POST /articles/company_aliases`

### Success HTTP response code

`201 Created`
