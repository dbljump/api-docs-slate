## Country subdivisions: get all

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "2940",
      "type": "places",
      "attributes": {
        "subtype": "subdivisions",
        "slug": "brand-new-subdivision-afghanistan",
        "name": "Brand New Subdivision",
        "short_name": null,
        "formatted": "Brand New Subdivision, Afghanistan",
        "latitude": 17.85,
        "longitude": -20,
        "also_known_as": [
          "That New Subdiv",
          "The New Subdiv"
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
        "country": {
          "data": {
            "id": "1",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/countries/afghanistan"
          }
        },
        "localities": {
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/brand-new-subdivision-afghanistan/localities"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/brand-new-subdivision-afghanistan"
      }
    },
    {
      "id": "2938",
      "type": "places",
      "attributes": {
        "subtype": "subdivisions",
        "slug": "new-subdivision-afghanistan",
        "name": "New Subdivision",
        "short_name": null,
        "formatted": "New Subdivision, Afghanistan",
        "latitude": 17.85,
        "longitude": -20,
        "also_known_as": [
          "That New Subdiv",
          "The New Subdiv"
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
        "country": {
          "data": {
            "id": "1",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/countries/afghanistan"
          }
        },
        "localities": {
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/new-subdivision-afghanistan/localities"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/new-subdivision-afghanistan"
      }
    },
    {
      "id": "2788",
      "type": "places",
      "attributes": {
        "subtype": "subdivisions",
        "slug": "western-afghanistan",
        "name": "Western",
        "short_name": null,
        "formatted": "Western, Afghanistan",
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
        "country": {
          "data": {
            "id": "1",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/countries/afghanistan"
          }
        },
        "localities": {
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/western-afghanistan/localities"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/western-afghanistan"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/places/countries/afghanistan/subdivisions?page%5Bnumber%5D=1&page%5Bsize%5D=3",
    "next": "http://api.dbljump.com/places/countries/afghanistan/subdivisions?page%5Bnumber%5D=2&page%5Bsize%5D=3",
    "last": "http://api.dbljump.com/places/countries/afghanistan/subdivisions?page%5Bnumber%5D=3&page%5Bsize%5D=3"
  },
  "meta": {
    "total_items": 9
  }
}
```

Retrieve all subdivisions belonging to the given country. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/countries/{country-slug}/subdivisions` (replace `{country-slug}` with country record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
