## <a name="countries_create"></a>Create a new country record

> Request body

```JSON
{
  "data": {
    "type": "places",
    "attributes": {
      "name": "New Country",
      "iso_code": "NC",
      "short_name": "NewC",
      "also_known_as": ["That New Country", "The New Place"],
      "latitude": "88.27",
      "longitude": "-150.55",
      "currency": "NCY",
      "nationality": "New Countryfolk"
    }
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "2937",
    "type": "place_countries",
    "attributes": {
      "slug": "new-country",
      "iso_code": "NC",
      "short_name": "NewC",
      "name": "New Country",
      "also_known_as": [
        "That New Country",
        "The New Place"
      ],
      "nationality": "New Countryfolk",
      "currency": "NCY",
      "longitude": -150.55,
      "latitude": 88.27,
      "created_at": "2017-03-10T15:27:13.797Z",
      "updated_at": "2017-03-10T15:27:13.797Z"
    },
    "relationships": {
      "created_by": {
        "data": {
          "id": "3",
          "type": "users"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/countries/new-country"
    }
  }
}
```

Create a new country record. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /places/countries`

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

`201 Created`
