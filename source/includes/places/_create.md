## <a name="places_create"></a>Create a new place record

> Request body | `POST /places`

```JSON
{
  "data": {
    "type": "places",
    "attributes": {
      "kind": "subdivision",
      "name": "Maryland",
      "short_name": "MD",
      "also_known_as": ["Old Line State", "Chesapeake Bay State"],
      "latitude": "38.0",
      "longitude": "-77.0",
      "iso_code": ""
    },
    "relationships": {
      "parent": {
        "data": {
          "id": "220",
          "type": "places"
        }
      }
    }
  }
}
```

> Response body | `HTTP 201`

```JSON
{
  "data": {
    "id": "2937",
    "type": "places",
    "attributes": {
      "kind": "subdivision",
      "slug": "maryland-united-states",
      "name": "Maryland",
      "short_name": "MD",
      "formatted": "Maryland, United States",
      "iso_code": "",
      "also_known_as": [
        "Old Line State",
        "Chesapeake Bay State"
      ],
      "nationality": "",
      "currency": "",
      "latitude": 38.0,
      "longitude": -77.0
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
      "parent": {
        "data": {
          "id": "220",
          "type": "users"
        },
        "links": {
          "related": "http://api.dbljump.com/places/united-states"
        }
      },
      "children": {
        "links": {
          "related": "http://api.dbljump.com/places/maryland-united-states/children"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/maryland-united-states"
    }
  },
  "included": [
    {
      "id": "2",
      "type": "users",
      "attributes": {
        "username": "neil",
        "role": "admin",
        "given_names": "Neil",
        "family_name": "Wheatley",
        "avatar": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1703301240.jpg"
      },
      "links": {
        "self": "http://api.dbljump.com/users/2"
      }
    }
  ],
  "meta": {
    "keywords": "maryland, md, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Maryland, United States at Dbljump.",
    "created_at": "2017-03-30T13:39:33.324Z",
    "updated_at": "2017-03-30T13:39:33.324Z"
  }
}
```

Create a new place record. Use the `kind` attribute to set whether the place is a region (i.e. a group of countries), country, subdivision (i.e. a state or county), or locality (i.e. a town or city). Admin-level authorization required, or editor-level if `kind == 'locality'`.

* User authentication: required
* Authorization level: admin for `region`, `country` or `subdivision`; editor for `locality` records.

### HTTP request

`POST /places`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
kind | string | Y | Must be 'region', 'country', 'subdivision', or 'locality'.
name | string | Y | Unique. 2-50 chars. English-language common name, e.g. 'United States'.
short_name | string | | Unique. 2-20 chars. Common short name, e.g. 'USA'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['US', 'America']`.
latitude | number | | Between -90 and 90.
longitude | number | | Between -180 and 180.
iso_code | string | Country-only | Unique. 2 chars. ISO 3166-1 country code.

### Relationships

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | ----------
parent | belongs_to | Subdivisions and localities only | places | The country a subdivision is in; the subdivision a locality is in.
children | has_many | | places | The countries inside a region.

### Success HTTP response code

`201 Created`
