## Get all platforms

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "1",
      "type": "platforms",
      "attributes": {
        "slug": "sony-playstation",
        "name": "PlayStation",
        "short_name": "PS",
        "sphere": "home",
        "kind": "system"
      },
      "relationships": {
        "holder": {
          "meta": {}
        },
        "parent": {
          "data": null,
          "links": {
            "related": "http://api.dbljump.com/platforms/sega-genesis"
          }
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
        "self": "http://api.dbljump.com/platforms/sony-playstation"
      }
    },
    {
      "id": "2",
      "type": "platforms",
      "attributes": {
        "slug": "sony-playstation-2",
        "name": "PlayStation 2",
        "short_name": "PS2",
        "sphere": "home",
        "kind": "system"
      },
      "relationships": {
        "holder": {
          "meta": {}
        },
        "parent": {
          "data": null,
          "links": {
            "related": "http://api.dbljump.com/platforms/sega-genesis"
          }
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
        "self": "http://api.dbljump.com/platforms/sony-playstation-2"
      }
    },
    {
      "id": "3",
      "type": "platforms",
      "attributes": {
        "slug": "sony-playstation-3",
        "name": "PlayStation 3",
        "short_name": "PS3",
        "sphere": "home",
        "kind": "system"
      },
      "relationships": {
        "holder": {
          "meta": {}
        },
        "parent": {
          "data": null,
          "links": {
            "related": "http://api.dbljump.com/platforms/sega-genesis"
          }
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
        "self": "http://api.dbljump.com/platforms/sony-playstation-3"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/platforms?page%5Bnumber%5D=1&page%5Bsize%5D=3",
    "next": "http://api.dbljump.com/platforms?page%5Bnumber%5D=2&page%5Bsize%5D=3",
    "last": "http://api.dbljump.com/platforms?page%5Bnumber%5D=13&page%5Bsize%5D=3"
  },
  "meta": {
    "total_items": 38
  }
}
```

Retrieve all platforms. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /platforms`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[platforms]=name,short_name`
filter[{field}] | All records | Filter search by field, e.g. `?filter[name]=Tokyo Prefecture`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
