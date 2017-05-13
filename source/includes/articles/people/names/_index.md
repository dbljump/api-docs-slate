## Get all of a company's names

> Response body | `HTTP 200`

```JSON
# GET /articles/companies/nintendo-co-ltd/names?page[size]=2

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

Retrieve all of a given company's names. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/companies/{company-slug}/names` (replace `{company-slug}` with parent company record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[company_names]=name`
filter[{field}] | All records | Filter search by field, e.g. `?filter[dropped]=true`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
