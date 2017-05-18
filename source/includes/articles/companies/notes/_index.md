## Get all of a company's titles

> Response body | `HTTP 200`

```JSON
# GET /articles/companies/nintendo-co-ltd/notes?page[size]=2

{
  "data": [
    {
      "id": "1",
      "type": "company_notes",
      "attributes": {
        "category": "History",
        "body": "Nintendo was a playing card manufacturer before it started making video games.",
        "cite_url": "",
        "cite_title": "",
        "cite_website": ""
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
    },
    {
      "id": "2",
      "type": "company_notes",
      "attributes": {
        "category": "Significance",
        "body": "The first video game console ever played in space was made by Nintendo. Aleksandr Serebrov played Tetris on a Game Boy.",
        "cite_url": "",
        "cite_title": "",
        "cite_website": ""
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
    "total_items": 3
  }
}
```

Retrieve all of a given company's notes. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/companies/{company-slug}/notes` (replace `{company-slug}` with parent company record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[company_notes]=body`
filter[{field}] | All records | Filter search by field, e.g. `?filter[category]=Hist`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
