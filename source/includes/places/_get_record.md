## Get single place

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "2894",
    "type": "place_localities",
    "attributes": {
      "name": "Austin",
      "formatted": "Austin, Texas, United States",
      "also_known_as": [],
      "latitude": null,
      "longitude": null
    },
    "relationships": {
      "subdivision": {
        "data": {
          "id": "2599",
          "type": "place_subdivisions"
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
      "self": "http://localhost:3000/places/localities/austin-texas-united-states",
      "subdivision": "http://localhost:3000/places/subdivisions/texas-united-states",
      "country": "http://localhost:3000/places/countries/united-states"
    }
  },
  "meta": {
    "keywords": "austin, texas, united states, city, town, place, city, town, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Austin, Texas, United States at Dbljump.",
    "created_at": "2017-03-06T14:49:29.207Z",
    "updated_at": "2017-03-06T14:49:29.207Z"
  }
}
```

Retrieve a single place record. Places are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/'slug'` (replace `slug` with place record slug)

### Success HTTP response code

`200 OK`

### Errors

HTTP code | Error code | Pointer | Title | Description
--------- | ---------- | ------- | ----- | -----------
404 | RECORD_NOT_FOUND | n/a | Record not found. |
