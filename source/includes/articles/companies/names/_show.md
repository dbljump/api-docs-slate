## <a name="company_names_show"></a>Get a single company name

> Response body | `HTTP 200`

```JSON
# GET /articles/company_names/5

{
  "data": {
    "id": "5",
    "type": "company_names",
    "attributes": {
      "name": "Nintendo",
      "kind": "styled",
      "writing_system": "Latin",
      "year_adopted": null,
      "dropped": null,
      "year_dropped": null
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
        "data": null
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
    }
  ],
  "meta": {
    "keywords": "nintendo, nintendo co., ltd., name, title, alias, dbljump, video games, pc games, gaming",
    "description": "Nintendo is an alternate name or title for Nintendo Co., Ltd.. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:13.793Z",
    "updated_at": "2017-04-24T09:09:13.793Z"
  }
}
```

Retrieve a single company name.

### HTTP request

`GET /articles/company_names/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`
