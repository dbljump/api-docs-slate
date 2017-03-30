## Country subdivisions: create new

> Request body

```JSON
{
  "data": {
    "type": "place_subdivisions",
    "attributes": {
      "name": "New Subdivision",
      "also_known_as": ["That New Subdiv", "The New Subdiv"],
      "latitude": "17.85",
      "longitude": "-20.00"
    }
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "2938",
    "type": "place_subdivisions",
    "attributes": {
      "name": "New Subdivision",
      "formatted": "New Subdivision, Afghanistan",
      "latitude": 17.85,
      "longitude": -20,
      "also_known_as": [
        "That New Subdiv",
        "The New Subdiv"
      ]
    },
    "relationships": {
      "country": {
        "data": {
          "id": "1",
          "type": "place_countries"
        }
      },
      "created_by": {
        "data": {
          "id": "3",
          "type": "users"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/subdivisions/new-subdivision-afghanistan",
      "country": "http://api.dbljump.com/places/countries/afghanistan"
    }
  }
}
```

Create a new subdivision record belonging to the given country. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /places/countries/{country-slug}/subdivisions` (replace `{country-slug}` with country record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | 2-250 chars. English-language common name, e.g. 'Florida'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['The Sunshine State']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Success HTTP response code

`201 Created`

### Errors

See [Places: subdivisions - Errors](#subdivs_errors).
