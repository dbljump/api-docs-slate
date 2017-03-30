## <a name="subdivs_show"></a>Get single subdivision

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "2599",
    "type": "place_subdivisions",
    "attributes": {
      "name": "Texas",
      "formatted": "Texas, United States",
      "latitude": 31.9685988,
      "longitude": -99.9018131,
      "also_known_as": []
    },
    "relationships": {
      "country": {
        "data": {
          "id": "220",
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
      "self": "http://api.dbljump.com/places/subdivisions/texas-united-states",
      "country": "http://api.dbljump.com/places/countries/united-states"
    }
  },
  "meta": {
    "keywords": "texas, united states, state, county, place, state, county, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Texas, United States at Dbljump.",
    "created_at": "2017-03-08T17:36:44.379Z",
    "updated_at": "2017-03-08T17:36:44.379Z"
  }
}
```

Retrieve a single subdivision record. Subdivisions are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/subdivisions/{slug}` (replace `{slug}` with subdivision record slug)

### Success HTTP response code

`200 OK`

### <a name="subdiv_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
subtype | string | Y | The place subclass. Always `subdivisions`.
slug | string | Y | A record ID based on the formatted name, e.g. `california-united-states`.
name | string | Y | English-language common name, e.g. `California`.
short_name | null | | Always `null`.
formatted | string | Y | The name and parent country name, e.g. `California, United States`.
latitude | number | | Global coordinate.
longitude | number | | Global coordinate.
also_known_as | array | | Other names the subdivision is known by, e.g. `['The Golden State']`.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
created_by | users | belongs_to
country | places (countries) | belongs_to
localities | places (localities) | has_many

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar
places (countries) | country | subtype, slug, name, short_name, formatted

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
