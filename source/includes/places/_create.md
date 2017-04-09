## <a name="places_create"></a>Create a new place record

> Request body

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
      "iso_code": "",
      "currency": "",
      "nationality": ""
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

> HTTP 201 response body

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
    },
    {
      "id": "1",
      "type": "places",
      "attributes": {
        "subtype": "country",
        "slug": "united-states",
        "name": "United States",
        "short_name": "USA",
        "formatted": "United States"
      },
      "links": {
        "self": "http://api.dbljump.com/places/united-states"
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

Create a new place record. Use the `kind` attribute to set whether the place is a region (i.e. a group of countries), country, subdivision (i.e. a state or county), or locality (i.e. a town or city). Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /places`

### Request attributes

We could cut the country-only `currency`, `iso_code` and `nationality` attributes, I don't know what we'll even use these for tbh.

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
kind | string | Y | Must be 'region', 'country', 'subdivision', or 'locality'.
name | string | Y | Unique. 2-50 chars. English-language common name, e.g. 'United States'.
short_name | string | | Unique. 2-20 chars. Common short name, e.g. 'USA'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['US', 'America']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.
currency | string | | COUNTRY ONLY. Must be 3 chars. ISO 4217 currency code, e.g. 'USD'.
iso_code | string | Y | COUNTRY ONLY. Unique. 2 chars. ISO 3166-1 country code.
nationality | string | | COUNTRY ONLY. 2-30 chars. English-lang common term, e.g. 'American'.

### Relationships

Country-region relationships would be handled with their own endpoint, probably `/places/relationships/country-regions`.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | ----------
parent | belongs_to | For subdivs and localities | places | The country a subdivision is in, or the subdivision a locality is in.
children | has_many | | places | The subdivs in a country, or the localities in a subdivision

### Success HTTP response code

`201 Created`
