## Get all person names

> Response body | `HTTP 200`

```JSON
# GET /articles/person_names?page[size]=2

{
  "data": [
    {
      "id": "41",
      "type": "person_names",
      "attributes": {
        "display_name": "岩田 聡",
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
    }
  ],
  "links": {},
  "meta": {
    "total_items": 1
  }
}
```

Retrieve all person names. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/person_names`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[person_names]=display_name`
filter[{field}] | All records | Filter search by field, e.g. `?filter[dropped]=true`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
