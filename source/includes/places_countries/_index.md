## Get all countries

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "232",
      "type": "place_countries",
      "attributes": {
        "slug": "zimbabwe",
        "iso_code": "ZW",
        "short_name": null,
        "name": "Zimbabwe",
        "also_known_as": [],
        "nationality": "Zimbabwean",
        "currency": null,
        "longitude": 30,
        "latitude": -20,
        "created_at": "2017-03-08T17:33:40.884Z",
        "updated_at": "2017-03-08T17:33:40.884Z"
      },
      "relationships": {
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/zimbabwe"
      }
    },
    {
      "id": "231",
      "type": "place_countries",
      "attributes": {
        "slug": "zambia",
        "iso_code": "ZM",
        "short_name": null,
        "name": "Zambia",
        "also_known_as": [],
        "nationality": "Zambian",
        "currency": null,
        "longitude": 30,
        "latitude": -15,
        "created_at": "2017-03-08T17:33:40.824Z",
        "updated_at": "2017-03-08T17:33:40.824Z"
      },
      "relationships": {
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/zambia"
      }
    },
    {
      "id": "230",
      "type": "place_countries",
      "attributes": {
        "slug": "yemen",
        "iso_code": "YE",
        "short_name": null,
        "name": "Yemen",
        "also_known_as": [],
        "nationality": "Yemeni",
        "currency": null,
        "longitude": 48,
        "latitude": 15,
        "created_at": "2017-03-08T17:33:40.755Z",
        "updated_at": "2017-03-08T17:33:40.755Z"
      },
      "relationships": {
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/yemen"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/places/countries?page%5Bnumber%5D=1&page%5Bsize%5D=30",
    "next": "http://api.dbljump.com/places/countries?page%5Bnumber%5D=2&page%5Bsize%5D=30",
    "last": "http://api.dbljump.com/places/countries?page%5Bnumber%5D=8&page%5Bsize%5D=30"
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
