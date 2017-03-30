## Get all localities

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "2936",
      "type": "places",
      "attributes": {
        "subtype": "localities",
        "slug": "matsumoto-nagano-prefecture-japan",
        "name": "Matsumoto",
        "short_name": null,
        "formatted": "Matsumoto, Nagano Prefecture, Japan",
        "also_known_as": [],
        "latitude": null,
        "longitude": null
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
        "country": {
          "data": {
            "id": "102",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/countries/japan"
          }
        },
        "subdivision": {
          "data": {
            "id": "1795",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/nagano-prefecture-japan"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/localities/matsumoto-nagano-prefecture-japan"
      }
    },
    {
      "id": "2935",
      "type": "places",
      "attributes": {
        "subtype": "localities",
        "slug": "nagano-nagano-prefecture-japan",
        "name": "Nagano",
        "short_name": null,
        "formatted": "Nagano, Nagano Prefecture, Japan",
        "also_known_as": [],
        "latitude": null,
        "longitude": null
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
        "country": {
          "data": {
            "id": "102",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/countries/japan"
          }
        },
        "subdivision": {
          "data": {
            "id": "1795",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/nagano-prefecture-japan"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/localities/nagano-nagano-prefecture-japan"
      }
    },
    {
      "id": "2934",
      "type": "places",
      "attributes": {
        "subtype": "localities",
        "slug": "sapporo-hokkaido-prefecture-japan",
        "name": "Sapporo",
        "short_name": null,
        "formatted": "Sapporo, Hokkaido Prefecture, Japan",
        "also_known_as": [],
        "latitude": null,
        "longitude": null
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
        "country": {
          "data": {
            "id": "102",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/countries/japan"
          }
        },
        "subdivision": {
          "data": {
            "id": "1232",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/hokkaido-prefecture-japan"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/localities/sapporo-hokkaido-prefecture-japan"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/places/localities?page%5Bnumber%5D=1&page%5Bsize%5D=3",
    "next": "http://api.dbljump.com/places/localities?page%5Bnumber%5D=2&page%5Bsize%5D=3",
    "last": "http://api.dbljump.com/places/localities?page%5Bnumber%5D=19&page%5Bsize%5D=3"
  },
  "meta": {
    "total_items": 56
  }
}
```

Retrieve all localities. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/localities`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
