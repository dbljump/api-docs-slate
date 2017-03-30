## <a name="countries_show"></a>Get single country

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "5",
    "type": "places",
    "attributes": {
      "subtype": "countries",
      "slug": "andorra",
      "name": "Andorra",
      "short_name": null,
      "formatted": "Andorra",
      "iso_code": "AD",
      "also_known_as": [],
      "nationality": "Andorran",
      "currency": null,
      "longitude": 1.3,
      "latitude": 42.3
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
      "regions": {
        "meta": {}
      },
      "subdivisions": {
        "links": {
          "related": "http://api.dbljump.com/places/countries/andorra/subdivisions"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/countries/andorra"
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
        "avatar": {
          "url": null
        }
      },
      "links": {
        "self": "http://api.dbljump.com/users/1"
      }
    }
  ],
  "meta": {
    "keywords": "andorra, ad, andorran, country, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Andorra at Dbljump.",
    "created_at": "2017-03-30T12:38:20.212Z",
    "updated_at": "2017-03-30T12:38:20.212Z"
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
users | created_by | username, role, given_names, family_name, avatar

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
