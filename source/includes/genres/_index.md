## Get all genres

> Response body | `HTTP 200`

```JSON
# GET /genres?page[size]=3

{
  "data": [
    {
      "id": "1",
      "type": "genres",
      "attributes": {
        "name": "action",
        "short_name": "",
        "also_known_as": [],
        "slug": "action"
      },
      "relationships": {
        "parent": {
          "data": null
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://api.dbljump.com/users/1"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/genres/action"
      }
    },
    {
      "id": "2",
      "type": "genres",
      "attributes": {
        "name": "adventure",
        "short_name": "",
        "also_known_as": [],
        "slug": "adventure"
      },
      "relationships": {
        "parent": {
          "data": null
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://api.dbljump.com/users/1"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/genres/adventure"
      }
    },
    {
      "id": "3",
      "type": "genres",
      "attributes": {
        "name": "art",
        "short_name": "",
        "also_known_as": [],
        "slug": "art"
      },
      "relationships": {
        "parent": {
          "data": null
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://api.dbljump.com/users/1"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/genres/art"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/genres?page%5Bnumber%5D=1&page%5Bsize%5D=3",
    "next": "http://api.dbljump.com/genres?page%5Bnumber%5D=2&page%5Bsize%5D=3",
    "last": "http://api.dbljump.com/genres?page%5Bnumber%5D=21&page%5Bsize%5D=3"
  },
  "meta": {
    "total_items": 63
  }
}
```

Retrieve all genres. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /genres`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[genres]=name`
filter[{field}] | All records | Filter search by field, e.g. `?filter[name]=action`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
