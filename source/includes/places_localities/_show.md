## <a name="localities_show"></a>Get single locality

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
      "self": "http://api.dbljump.com/places/localities/austin-texas-united-states",
      "subdivision": "http://api.dbljump.com/places/subdivisions/texas-united-states",
      "country": "http://api.dbljump.com/places/countries/united-states"
    }
  },
  "meta": {
    "keywords": "austin, texas, united states, city, town, place, city, town, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Austin, Texas, United States at Dbljump.",
    "created_at": "2017-03-08T17:37:15.372Z",
    "updated_at": "2017-03-08T17:37:15.372Z"
  }
}
```

Retrieve a single locality record. Localities are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/localities/{slug}` (replace `{slug}` with locality record slug)

### Success HTTP response code

`200 OK`

### <a name="subdiv_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
subtype | string | Y | The place subclass. Always `localities`.
slug | string | Y | A record ID based on the formatted name, e.g. `los-angeles-california-united-states`.
name | string | Y | English-language common name, e.g. `Los Angeles`.
short_name | null | | Always `null`.
formatted | string | Y | The name and parent subdivision and country names, e.g. `Los Angeles, California, United States`.
latitude | number | | Global coordinate.
longitude | number | | Global coordinate.
also_known_as | array | | Other names the locality is known by, e.g. `['LA', 'City of Angels']`.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
created_by | users | belongs_to
country | places (countries) | belongs_to
subdivision | places (subdivisions) | belongs_to

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar
places (countries) | country | subtype, slug, name, short_name, formatted
places (subdivisions) | country | subtype, slug, name, short_name, formatted

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
