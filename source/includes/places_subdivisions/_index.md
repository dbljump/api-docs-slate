## Get all subdivisions

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "240",
      "type": "place_subdivisions",
      "attributes": {
        "name": "All",
        "formatted": "All, Niue",
        "latitude": null,
        "longitude": null,
        "also_known_as": []
      },
      "relationships": {
        "country": {
          "data": {
            "id": "151",
            "type": "place_countries"
          }
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/0-niue",
        "country": "http://api.dbljump.com/places/countries/niue"
      }
    },
    {
      "id": "241",
      "type": "place_subdivisions",
      "attributes": {
        "name": "All",
        "formatted": "All, Curaçao",
        "latitude": null,
        "longitude": null,
        "also_known_as": []
      },
      "relationships": {
        "country": {
          "data": {
            "id": "53",
            "type": "place_countries"
          }
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/0-curacao",
        "country": "http://api.dbljump.com/places/countries/curacao"
      }
    },
    {
      "id": "242",
      "type": "place_subdivisions",
      "attributes": {
        "name": "All",
        "formatted": "All, Bermuda",
        "latitude": null,
        "longitude": null,
        "also_known_as": []
      },
      "relationships": {
        "country": {
          "data": {
            "id": "23",
            "type": "place_countries"
          }
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/0-bermuda",
        "country": "http://api.dbljump.com/places/countries/bermuda"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/places/subdivisions?page%5Bnumber%5D=1&page%5Bsize%5D=30",
    "next": "http://api.dbljump.com/places/subdivisions?page%5Bnumber%5D=2&page%5Bsize%5D=30",
    "last": "http://api.dbljump.com/places/subdivisions?page%5Bnumber%5D=89&page%5Bsize%5D=30"
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
