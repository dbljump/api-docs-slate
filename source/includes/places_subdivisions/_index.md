## Get all subdivisions

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "2237",
      "type": "places",
      "attributes": {
        "subtype": "subdivisions",
        "slug": "sabha-libya",
        "name": "Sabha",
        "short_name": null,
        "formatted": "Sabha, Libya",
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
            "id": "117",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/countries/libya"
          }
        },
        "localities": {
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/sabha-libya/localities"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/sabha-libya"
      }
    },
    {
      "id": "240",
      "type": "places",
      "attributes": {
        "subtype": "subdivisions",
        "slug": "0-niue",
        "name": "All",
        "short_name": null,
        "formatted": "All, Niue",
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
            "id": "151",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/countries/niue"
          }
        },
        "localities": {
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/0-niue/localities"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/0-niue"
      }
    },
    {
      "id": "241",
      "type": "places",
      "attributes": {
        "subtype": "subdivisions",
        "slug": "0-curacao",
        "name": "All",
        "short_name": null,
        "formatted": "All, Curaçao",
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
            "id": "53",
            "type": "places"
          },
          "links": {
            "related": "http://api.dbljump.com/places/countries/curacao"
          }
        },
        "localities": {
          "links": {
            "related": "http://api.dbljump.com/places/subdivisions/0-curacao/localities"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/0-curacao"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/places/subdivisions?page%5Bnumber%5D=1&page%5Bsize%5D=3",
    "next": "http://api.dbljump.com/places/subdivisions?page%5Bnumber%5D=2&page%5Bsize%5D=3",
    "last": "http://api.dbljump.com/places/subdivisions?page%5Bnumber%5D=881&page%5Bsize%5D=3"
  },
  "meta": {
    "total_items": 2641
  }
}
```

Retrieve all subdivisions. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/subdivisions`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
