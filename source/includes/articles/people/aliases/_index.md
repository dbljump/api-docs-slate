## Get all person aliases

> Response body | `HTTP 200`

```JSON
# GET /articles/person_aliases?page[size]=2

{
  "data": [
    {
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
    }
  ],
  "links": {},
  "meta": {
    "total_items": 1
  }
}
```

Retrieve all person aliases. Automatically paginated.

### HTTP request

`GET /articles/person_aliases`

### Success HTTP response code

`200 OK`
