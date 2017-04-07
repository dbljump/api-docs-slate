## Get all regions

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "2937",
      "type": "places",
      "attributes": {
        "subtype": "regions",
        "slug": "new-region",
        "name": "New Region",
        "short_name": "NR",
        "formatted": "New Region",
        "latitude": 5,
        "longitude": -35,
        "also_known_as": [
          "That New Region",
          "The Newest"
        ]
      },
      "relationships": {
        "created_by": {
          "data": {
            "id": "2",
            "type": "users"
          },
          "links": {
            "related": "http://api.dbljump.com/users/2"
          }
        },
        "countries": {
          "data": [
            {
              "id": "7",
              "type": "places"
            },
            {
              "id": "27",
              "type": "places"
            }
          ],
          "links": {
            "related": "http://api.dbljump.com/places/regions/new-region/countries"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/regions/new-region"
      }
    },
    {
      "id": "239",
      "type": "places",
      "attributes": {
        "subtype": "regions",
        "slug": "australia-and-new-zealand",
        "name": "Australia and New Zealand",
        "short_name": "Aus&NZ",
        "formatted": "Australia and New Zealand",
        "latitude": null,
        "longitude": null,
        "also_known_as": []
      },
      "relationships": {
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://api.dbljump.com/users/1"
          }
        },
        "countries": {
          "data": [
            {
              "id": "12",
              "type": "places"
            },
            {
              "id": "147",
              "type": "places"
            }
          ],
          "links": {
            "related": "http://api.dbljump.com/places/regions/australia-and-new-zealand/countries"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/regions/australia-and-new-zealand"
      }
    },
    {
      "id": "238",
      "type": "places",
      "attributes": {
        "subtype": "regions",
        "slug": "us-and-canada",
        "name": "US and Canada",
        "short_name": "US&Ca",
        "formatted": "US and Canada",
        "latitude": null,
        "longitude": null,
        "also_known_as": []
      },
      "relationships": {
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://api.dbljump.com/users/1"
          }
        },
        "countries": {
          "data": [
            {
              "id": "36",
              "type": "places"
            },
            {
              "id": "220",
              "type": "places"
            }
          ],
          "links": {
            "related": "http://api.dbljump.com/places/regions/us-and-canada/countries"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/regions/us-and-canada"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/places/regions?page%5Bnumber%5D=1&page%5Bsize%5D=3",
    "next": "http://api.dbljump.com/places/regions?page%5Bnumber%5D=2&page%5Bsize%5D=3",
    "last": "http://api.dbljump.com/places/regions?page%5Bnumber%5D=3&page%5Bsize%5D=3"
  },
  "meta": {
    "total_items": 8
  }
}
```

Retrieve all regions. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/regions`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
