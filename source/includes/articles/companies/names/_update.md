## <a name="company_names_update"></a>Update a company name

> Request body | `PATCH /articles/company_names/7`

```JSON
{
  "data": {
    "type": "company_names",
    "id": "7",
    "attributes": {
      "name": "アップデート",
      "kind": "styled",
      "writing_system": "Japanese",
      "year_adopted": "1995",
      "dropped": "true",
      "year_dropped": ""
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

> Response body | `HTTP 200`

```JSON
{
  "data": {
    "id": "7",
    "type": "company_names",
    "attributes": {
      "name": "アップデート",
      "kind": "styled",
      "writing_system": "Japanese",
      "year_adopted": 1995,
      "dropped": true,
      "year_dropped": null
    },
    "relationships": {
      "company": {
        "data": {
          "id": "2",
          "type": "companies"
        },
        "links": {
          "related": "http://localhost:3000/articles/companies/sega-games-co-ltd"
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
      "id": "2",
      "type": "companies",
      "attributes": {
        "display_title": "Sega Games Co., Ltd."
      },
      "links": {
        "self": "http://localhost:3000/articles/companies/sega-games-co-ltd"
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
    "keywords": "アップデート, sega games co., ltd., japan, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "アップデート is an alternate name or title for Sega Games Co., Ltd.. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:13.815Z",
    "updated_at": "2017-05-03T10:28:40.939Z"
  }
}
```

Update an existing company name. The user must be an editor or admin.

The `company` relationship cannot be updated.

### HTTP request

`PATCH /articles/company_names/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`
