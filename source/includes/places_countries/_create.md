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
    "type": "places",
    "attributes": {
      "subtype": "countries",
      "slug": "new-country",
      "name": "New Country",
      "short_name": "NewC",
      "formatted": "New Country",
      "iso_code": "NC",
      "also_known_as": [
        "That New Country",
        "The New Place"
      ],
      "nationality": "New Countryfolk",
      "currency": "NCY",
      "longitude": -150.55,
      "latitude": 88.27
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
      "regions": {
        "meta": {}
      },
      "subdivisions": {
        "links": {
          "related": "http://api.dbljump.com/places/countries/new-country/subdivisions"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/countries/new-country"
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
    "keywords": "new country, newc, that new country, the new place, nc, new countryfolk, country, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from New Country at Dbljump.",
    "created_at": "2017-03-30T13:39:33.324Z",
    "updated_at": "2017-03-30T13:39:33.324Z"
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
name | string | Y | Unique. 2-50 chars. English-language common name, e.g. 'United States'.
iso_code | string | Y | Unique. 2 chars. ISO 3166-1 country code.
short_name | string | | Unique. 2-20 chars. Common short name, e.g. 'USA'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['US', 'America']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.
currency | string | | Must be 3 chars. ISO 4217 currency code, e.g. 'USD'.
nationality | string | | 2-30 chars. English-lang common term, e.g. 'American'.

### Success HTTP response code

`201 Created`
