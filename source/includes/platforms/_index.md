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
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of platforms per page

### Success HTTP response code

`200 OK`
