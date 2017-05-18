## Get all of a person's titles

> Response body | `HTTP 200`

```JSON
# GET /articles/people/shigeru-miyamoto/notes?page[size]=2

{
  "data": [
    {
      "id": "6",
      "type": "person_notes",
      "attributes": {
        "category": "Education",
        "body": "Studied industrial design at Kanazawa Municipal College of Industrial Arts.",
        "cite_url": "",
        "cite_title": "",
        "cite_website": ""
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
        "created_by": {
          "data": {
            "id": "1",
            "type": "created_bies"
          },
          "links": {
            "related": "http://localhost:3000/users/1"
          }
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

Retrieve all of a given person's notes. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/companies/{person-slug}/notes` (replace `{person-slug}` with parent person record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[person_notes]=body`
filter[{field}] | All records | Filter search by field, e.g. `?filter[category]=Personal`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
