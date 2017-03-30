## Subdivision localities: create new

> Request body

```JSON
{
  "data": {
    "type": "place_localities",
    "id": "texas-united-states",
    "attributes": {
      "name": "New City",
      "also_known_as": ["That New City", "The New Locality"],
      "latitude": "70.3",
      "longitude": "-45.5"
    }
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "2937",
    "type": "place_localities",
    "attributes": {
      "slug": "new-city-texas-united-states",
      "name": "New City",
      "formatted": "New City, Texas, United States",
      "also_known_as": [
        "That New City",
        "The New Locality"
      ],
      "latitude": 70.3,
      "longitude": -45.5
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
          "id": "220",
          "type": "place_countries"
        },
        "links": {
          "related": "http://api.dbljump.com/places/countries/united-states"
        }
      },
      "subdivision": {
        "data": {
          "id": "2599",
          "type": "place_subdivisions"
        },
        "links": {
          "related": "http://api.dbljump.com/places/subdivisions/texas-united-states"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/localities/new-city-texas-united-states"
    }
  }
}
```

Create a new locality record belonging to the given subdivision. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /places/subdivisions/{subdivision-slug}/localities` (replace `{subdivision-slug}` with subdivision record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | 2-250 chars. English-language common name, e.g. 'Los Angeles'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['LA', 'City of Angels']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Success HTTP response code

`201 Created`

### Errors

See [Places:localities - Errors](#localities_errors).
