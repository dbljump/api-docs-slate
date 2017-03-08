## Get all places

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "1",
      "type": "place_countries",
      "attributes": {
        "slug": "afghanistan",
        "iso_code": "AF",
        "short_name": null,
        "name": "Afghanistan",
        "also_known_as": [],
        "nationality": "Afghan",
        "currency": null,
        "longitude": 65,
        "latitude": 33,
        "created_at": "2017-03-06T14:48:43.442Z",
        "updated_at": "2017-03-06T14:48:43.442Z"
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
        "self": "http://localhost:3000/places/countries/afghanistan"
      }
    },
    {
      "id": "2",
      "type": "place_countries",
      "attributes": {
        "slug": "albania",
        "iso_code": "AL",
        "short_name": null,
        "name": "Albania",
        "also_known_as": [],
        "nationality": "Albanian",
        "currency": null,
        "longitude": 20,
        "latitude": 41,
        "created_at": "2017-03-06T14:48:43.485Z",
        "updated_at": "2017-03-06T14:48:43.485Z"
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
        "self": "http://localhost:3000/places/countries/albania"
      }
    },
    {
      "id": "3",
      "type": "place_countries",
      "attributes": {
        "slug": "algeria",
        "iso_code": "DZ",
        "short_name": null,
        "name": "Algeria",
        "also_known_as": [],
        "nationality": "Algerian",
        "currency": null,
        "longitude": 3,
        "latitude": 28,
        "created_at": "2017-03-06T14:48:43.509Z",
        "updated_at": "2017-03-06T14:48:43.509Z"
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
        "self": "http://localhost:3000/places/countries/algeria"
      }
    }
  ],
  "links": {
    "self": "http://localhost:3000/places?page%5Bnumber%5D=1&page%5Bsize%5D=30",
    "next": "http://localhost:3000/places?page%5Bnumber%5D=2&page%5Bsize%5D=30",
    "last": "http://localhost:3000/places?page%5Bnumber%5D=98&page%5Bsize%5D=30"
  },
  "meta": {
    "total_items": 2
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
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
