## <a name="subdivs_update"></a>Update a subdivision record

> Request body

```JSON
{
  "data": {
    "type": "place_subdivisions",
    "id": "north-puerto-rico",
    "attributes": {
      "country_id": "10",
      "name": "Updated Subdivision",
      "also_known_as": ["Updated Subdiv", "Changed Subdiv"],
      "latitude": "3.0",
      "longitude": "-25.00"
    }
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "269",
    "type": "place_subdivisions",
    "attributes": {
      "name": "Updated Subdivision",
      "formatted": "Updated Subdivision, Armenia",
      "latitude": 3,
      "longitude": -25,
      "also_known_as": [
        "Updated Subdiv",
        "Changed Subdiv"
      ]
    },
    "relationships": {
      "country": {
        "data": {
          "id": "10",
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
      "self": "http://api.dbljump.com/places/subdivisions/updated-subdivision-armenia",
      "country": "http://api.dbljump.com/places/countries/armenia"
    }
  }
}
```

Update an existing subdivision record. The user must be an admin.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /places/subdivisions/{slug}` (replace `{slug}` with subdivision record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
country_id | integer | Y | ID of parent country.
name | string | Y | 2-250 chars. English-language common name, e.g. 'Florida'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['The Sunshine State']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Success HTTP response code

`200 OK`
