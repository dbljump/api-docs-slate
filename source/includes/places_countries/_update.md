## Update a country record

> Request body

```JSON
{
  "data": {
    "type": "place_countries",
    "id": "andorra",
    "attributes": {
      "name": "Updated Country",
      "iso_code": "UP",
      "short_name": "Updated",
      "also_known_as": ["Edited Country", "Renamed Country"],
      "latitude": "5.0",
      "longitude": "10.0",
      "currency": "UPD",
      "nationality": "Updatedfolk"
    }
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "5",
    "type": "place_countries",
    "attributes": {
      "slug": "updated-country",
      "iso_code": "UP",
      "short_name": "Updated",
      "name": "Updated Country",
      "also_known_as": [
        "Edited Country",
        "Renamed Country"
      ],
      "nationality": "Updatedfolk",
      "currency": "UPD",
      "longitude": 10,
      "latitude": 5,
      "created_at": "2017-03-08T17:33:23.051Z",
      "updated_at": "2017-03-10T17:17:07.482Z"
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
      "self": "http://api.dbljump.com/places/countries/updated-country"
    }
  }
}
```

Update an existing country record. The user must be an admin.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /places/countries/{slug}` (replace `{slug}` with country record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | Unique. 2-250 chars. English-language common name, e.g. 'United States'.
iso_code | string | Y | Unique. 2 chars. ISO 3166-1 country code.
short_name | string | | Unique. 2-20 chars. Common short name, e.g. 'USA'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['US', 'America']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.
currency | string | | Must be 3 chars. ISO 4217 currency code, e.g. 'USD'.
nationality | string | | 2-30 chars. English-lang common term, e.g. 'American'.

### Success HTTP response code

`200 OK`
