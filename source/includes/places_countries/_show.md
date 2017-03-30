## <a name="countries_show"></a>Get single country

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "220",
    "type": "place_countries",
    "attributes": {
      "slug": "united-states",
      "iso_code": "US",
      "short_name": "USA",
      "name": "United States",
      "also_known_as": [],
      "nationality": "American",
      "currency": null,
      "longitude": -97,
      "latitude": 38,
      "created_at": "2017-03-08T17:33:40.235Z",
      "updated_at": "2017-03-08T17:33:40.235Z"
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
      "self": "http://api.dbljump.com/places/countries/united-states"
    }
  },
  "meta": {
    "keywords": "united states, usa, us, american, country, place, country, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from United States at Dbljump.",
    "created_at": "2017-03-08T17:33:40.235Z",
    "updated_at": "2017-03-08T17:33:40.235Z"
  }
}
```

Retrieve a single country record. Countries are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/countries/{slug}` (replace `{slug}` with country record slug)

### Success HTTP response code

`200 OK`

### <a name="country_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
subtype | string | Y | The place subclass. Always 'countries'.
slug | string | Y | A record ID based on the formatted name, e.g. 'united-states'.
name | string | Y | English-language common name, e.g. 'United States'.
iso_code | string | Y | The country's ISO 3166-1 country code.
short_name | string | | A common short name, e.g. 'USA'.
formatted | string | Y | Has the same value as `name`.
also_known_as | array | | Other names the country is known by, e.g. `['US', 'America']`.
latitude | number/float | | Global coordinate.
longitude | number/float | | Global coordinate.
currency | string | | The national currency's ISO 4217 code, e.g. 'USD'.
nationality | string | | Nationality of inhabitants, e.g. 'American'.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
created_by | users | belongs_to
regions | places (regions) | has_many

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | uploaded_by | username, role, given_names, family_name, avatar

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
