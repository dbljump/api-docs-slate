## Subdivision localities: get all

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "2925",
      "type": "places",
      "attributes": {
        "subtype": "localities",
        "slug": "tokyo-tokyo-prefecture-japan",
        "name": "Tokyo",
        "short_name": null,
        "formatted": "Tokyo, Tokyo Prefecture, Japan",
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
            "id": "2627",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/tokyo-prefecture-japan"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/localities/tokyo-tokyo-prefecture-japan"
      }
    },
    {
      "id": "2926",
      "type": "places",
      "attributes": {
        "subtype": "localities",
        "slug": "chiyoda-tokyo-prefecture-japan",
        "name": "Chiyoda",
        "short_name": null,
        "formatted": "Chiyoda, Tokyo Prefecture, Japan",
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
            "id": "2627",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/tokyo-prefecture-japan"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/localities/chiyoda-tokyo-prefecture-japan"
      }
    },
    {
      "id": "2927",
      "type": "places",
      "attributes": {
        "subtype": "localities",
        "slug": "minato-tokyo-prefecture-japan",
        "name": "Minato",
        "short_name": null,
        "formatted": "Minato, Tokyo Prefecture, Japan",
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
            "id": "2627",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/tokyo-prefecture-japan"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/localities/minato-tokyo-prefecture-japan"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/places/subdivisions/tokyo-prefecture-japan/localities?page%5Bnumber%5D=1&page%5Bsize%5D=3",
    "next": "http://api.dbljump.com/places/subdivisions/tokyo-prefecture-japan/localities?page%5Bnumber%5D=2&page%5Bsize%5D=3",
    "last": "http://api.dbljump.com/places/subdivisions/tokyo-prefecture-japan/localities?page%5Bnumber%5D=2&page%5Bsize%5D=3"
  },
  "meta": {
    "total_items": 5
  }
}
```

Retrieve all localities belonging to the given subdivision. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/subdivisions/{subdivision-slug}/localities` (replace `{subdivision-slug}` with subdivision record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
