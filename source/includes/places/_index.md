## <a name="places_index"></a>Get all places

> Response body | `HTTP 200`

```JSON
# GET /places?page[size]=2&filter[kind]=subdivision

{
  "data": [
    {
      "id": "2237",
      "type": "places",
      "attributes": {
        "kind": "subdivision",
        "slug": "sabha-libya",
        "name": "Sabha",
        "formatted": "Sabha, Libya",
        "short_name": null,
        "also_known_as": [],
        "latitude": null,
        "longitude": null,
        "iso_code": null
      },
      "relationships": {
        "parent": {
          "data": {
            "id": "117",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/libya"
          }
        },
        "children": {
          "data": [],
          "links": {
            "related": "http://api.dbljump.com/places/sabha-libya/children"
          }
        },
        "regions": {
          "data": [
            {
              "id": "236",
              "type": "places"
            }
          ],
          "links": {
            "related": "http://api.dbljump.com/places/sabha-libya/regions"
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
        "self": "http://api.dbljump.com/places/sabha-libya"
      }
    },
    {
      "id": "240",
      "type": "places",
      "attributes": {
        "kind": "subdivision",
        "slug": "0-niue",
        "name": "All",
        "formatted": "All, Niue",
        "short_name": null,
        "also_known_as": [],
        "latitude": null,
        "longitude": null,
        "iso_code": null
      },
      "relationships": {
        "parent": {
          "data": {
            "id": "151",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/niue"
          }
        },
        "children": {
          "data": [],
          "links": {
            "related": "http://api.dbljump.com/places/0-niue/children"
          }
        },
        "regions": {
          "data": [],
          "links": {
            "related": "http://api.dbljump.com/places/0-niue/regions"
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
        "self": "http://api.dbljump.com/places/0-niue"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/places?filter%5Bkind%5D=subdivision&page%5Bnumber%5D=1&page%5Bsize%5D=2",
    "next": "http://api.dbljump.com/places?filter%5Bkind%5D=subdivision&page%5Bnumber%5D=2&page%5Bsize%5D=2",
    "last": "http://api.dbljump.com/places?filter%5Bkind%5D=subdivision&page%5Bnumber%5D=1321&page%5Bsize%5D=2"
  },
  "meta": {
    "total_items": 2937
  }
}
```

Retrieve all places. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[places] | All fields | Return only specified fields, e.g. `/places?fields[places]=name,formatted`
filter[field] | null | Filter search by field, e.g. `/places?filter[kind]=country,region`
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
