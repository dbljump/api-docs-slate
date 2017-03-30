## Get all countries

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "232",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "zimbabwe",
        "name": "Zimbabwe",
        "short_name": null,
        "formatted": "Zimbabwe",
        "iso_code": "ZW",
        "also_known_as": [],
        "nationality": "Zimbabwean",
        "currency": null,
        "longitude": 30,
        "latitude": -20
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
        "regions": {
          "meta": {}
        },
        "subdivisions": {
          "links": {
            "related": "http://api.dbljump.com/places/countries/zimbabwe/subdivisions"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/zimbabwe"
      }
    },
    {
      "id": "231",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "zambia",
        "name": "Zambia",
        "short_name": null,
        "formatted": "Zambia",
        "iso_code": "ZM",
        "also_known_as": [],
        "nationality": "Zambian",
        "currency": null,
        "longitude": 30,
        "latitude": -15
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
        "regions": {
          "meta": {}
        },
        "subdivisions": {
          "links": {
            "related": "http://api.dbljump.com/places/countries/zambia/subdivisions"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/zambia"
      }
    },
    {
      "id": "230",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "yemen",
        "name": "Yemen",
        "short_name": null,
        "formatted": "Yemen",
        "iso_code": "YE",
        "also_known_as": [],
        "nationality": "Yemeni",
        "currency": null,
        "longitude": 48,
        "latitude": 15
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
        "regions": {
          "meta": {}
        },
        "subdivisions": {
          "links": {
            "related": "http://api.dbljump.com/places/countries/yemen/subdivisions"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/yemen"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/places/countries?page%5Bnumber%5D=1&page%5Bsize%5D=3",
    "next": "http://api.dbljump.com/places/countries?page%5Bnumber%5D=2&page%5Bsize%5D=3",
    "last": "http://api.dbljump.com/places/countries?page%5Bnumber%5D=78&page%5Bsize%5D=3"
  },
  "meta": {
    "total_items": 232
  }
}
```

Retrieve all countries. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/countries`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
