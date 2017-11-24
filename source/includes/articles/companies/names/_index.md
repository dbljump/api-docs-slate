## Get company names

> Response body | `HTTP 200`

```JSON
# GET /articles/company_names?page[size]=2

{
  "data": [
    {
      "id": "1",
      "type": "company_names",
      "attributes": {
        "name": "任天堂株式会社",
        "kind": "name",
        "writing_system": "Japanese",
        "year_adopted": null,
        "dropped": null,
        "year_dropped": null
      },
      "relationships": {
        "place": {
          "data": null
        }
      }
    },
    {
      "id": "2",
      "type": "company_names",
      "attributes": {
        "name": "Nintendō Kabushiki gaisha",
        "kind": "name",
        "writing_system": "Latin",
        "year_adopted": null,
        "dropped": true,
        "year_dropped": null
      },
      "relationships": {
        "place": {
          "data": null
        }
      }
    }
  ],
  "links": {
    "self": "http://localhost:3000/articles/companies/nintendo-co-ltd/names?page%5Bnumber%5D=1&page%5Bsize%5D=2",
    "next": "http://localhost:3000/articles/companies/nintendo-co-ltd/names?page%5Bnumber%5D=2&page%5Bsize%5D=2",
    "last": "http://localhost:3000/articles/companies/nintendo-co-ltd/names?page%5Bnumber%5D=3&page%5Bsize%5D=2"
  },
  "meta": {
    "total_items": 5
  }
}
```

Retrieve a collection of company names.

### HTTP request

`GET /articles/company_names`

### Filter fields

* `company_id`
* `display_text`
* `kind`
* `writing_system`
* `year_adopted`
* `year_dropped`
* `dropped`

### Sort fields

* `company_id`
* `display_text`
* `kind`
* `writing_system`
* `year_adopted`
* `year_dropped`
* `dropped`

### Success HTTP response code

`200 OK`
