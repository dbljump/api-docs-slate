## Get all companies

> Response body | `HTTP 200`

```JSON
# GET /articles/companies?page[size]=2

{
  "data": [
    {
      "id": "20",
      "type": "companies",
      "attributes": {
        "display_title": "Google Inc.",
        "description": "Google is an American technology company best known in the gaming world for its Android mobile platform.",
        "origin_date": null,
        "origin_year": 1998,
        "end": null,
        "end_date": null,
        "end_year": null,
        "slug": "google-inc"
      },
      "relationships": {
        "origin_place": {
          "data": {
            "id": "2888",
            "type": "places"
          },
          "links": {
            "related": "http://localhost:3000/places/mountain-view-california-united-states"
          }
        },
        "latest_place": {
          "data": null
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://localhost:3000/users/1"
          }
        }
      },
      "links": {
        "self": "http://localhost:3000/articles/companies/google-inc"
      }
    },
    {
      "id": "19",
      "type": "companies",
      "attributes": {
        "display_title": "Apple Inc.",
        "description": "Apple is an American technology company best known within the gaming world for its iOS and Mac platforms.",
        "origin_date": null,
        "origin_year": 1976,
        "end": null,
        "end_date": null,
        "end_year": null,
        "slug": "apple-inc"
      },
      "relationships": {
        "origin_place": {
          "data": {
            "id": "2887",
            "type": "places"
          },
          "links": {
            "related": "http://localhost:3000/places/cupertino-california-united-states"
          }
        },
        "latest_place": {
          "data": null
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://localhost:3000/users/1"
          }
        }
      },
      "links": {
        "self": "http://localhost:3000/articles/companies/apple-inc"
      }
    }
  ],
  "links": {
    "self": "http://localhost:3000/articles/companies?page%5Bnumber%5D=1&page%5Bsize%5D=2",
    "next": "http://localhost:3000/articles/companies?page%5Bnumber%5D=2&page%5Bsize%5D=2",
    "last": "http://localhost:3000/articles/companies?page%5Bnumber%5D=10&page%5Bsize%5D=2"
  },
  "meta": {
    "total_items": 20
  }
}
```

Retrieve all company articles. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/companies`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[companies]=display_title,description`
filter[{field}] | All records | Filter search by field, e.g. `?filter[end]=true`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
