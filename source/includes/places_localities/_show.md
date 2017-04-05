## <a name="localities_show"></a>Get single locality

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "2936",
    "type": "places",
    "attributes": {
      "subtype": "localities",
      "slug": "matsumoto-nagano-prefecture-japan",
      "name": "Matsumoto",
      "short_name": null,
      "formatted": "Matsumoto, Nagano Prefecture, Japan",
      "also_known_as": [],
      "latitude": null,
      "longitude": null
    },
    "relationships": {
      "created_by": {
        "data": {
          "id": "1",
          "type": "users"
        },
        "links": {
          "related": "http://api.dbljump.com/users/1"
        }
      },
      "country": {
        "data": {
          "id": "102",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/countries/japan"
        }
      },
      "subdivision": {
        "data": {
          "id": "1795",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/subdivisions/nagano-prefecture-japan"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/localities/matsumoto-nagano-prefecture-japan"
    }
  },
  "included": [
    {
      "id": "1",
      "type": "users",
      "attributes": {
        "username": "tikithekiwi",
        "role": "admin",
        "given_names": "Tiki",
        "family_name": "the Kiwi",
        "avatar": null
      },
      "links": {
        "self": "http://api.dbljump.com/users/1"
      }
    },
    {
      "id": "102",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "japan",
        "name": "Japan",
        "short_name": null,
        "formatted": "Japan"
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/japan"
      }
    },
    {
      "id": "1795",
      "type": "places",
      "attributes": {
        "subtype": "subdivisions",
        "slug": "nagano-prefecture-japan",
        "name": "Nagano Prefecture",
        "short_name": null,
        "formatted": "Nagano Prefecture, Japan"
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/nagano-prefecture-japan"
      }
    }
  ],
  "meta": {
    "keywords": "matsumoto, nagano prefecture, japan, city, town, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Matsumoto, Nagano Prefecture, Japan at Dbljump.",
    "created_at": "2017-03-30T12:40:07.612Z",
    "updated_at": "2017-03-30T12:40:07.612Z"
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
