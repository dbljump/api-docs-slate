## Country subdivisions: create new

> Request body

```JSON
{
  "data": {
    "type": "places",
    "attributes": {
      "name": "Brand New Subdivision",
      "also_known_as": ["That New Subdiv", "The New Subdiv"],
      "latitude": "17.85",
      "longitude": "-20.00"
    }
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "2940",
    "type": "places",
    "attributes": {
      "subtype": "subdivisions",
      "slug": "brand-new-subdivision-afghanistan",
      "name": "Brand New Subdivision",
      "short_name": null,
      "formatted": "Brand New Subdivision, Afghanistan",
      "latitude": 17.85,
      "longitude": -20,
      "also_known_as": [
        "That New Subdiv",
        "The New Subdiv"
      ]
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
      "country": {
        "data": {
          "id": "1",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/countries/afghanistan"
        }
      },
      "localities": {
        "links": {
          "related": "http://api.dbljump.com/places/subdivisions/brand-new-subdivision-afghanistan/localities"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/subdivisions/brand-new-subdivision-afghanistan"
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
        "subtype": "countries",
        "slug": "afghanistan",
        "name": "Afghanistan",
        "short_name": null,
        "formatted": "Afghanistan"
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/afghanistan"
      }
    }
  ],
  "meta": {
    "keywords": "brand new subdivision, afghanistan, that new subdiv, the new subdiv, state, county, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Brand New Subdivision, Afghanistan at Dbljump.",
    "created_at": "2017-03-30T13:54:19.505Z",
    "updated_at": "2017-03-30T13:54:19.505Z"
  }
}
```

Create a new subdivision record belonging to the given country. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /places/countries/{country-slug}/subdivisions` (replace `{country-slug}` with country record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | 2-250 chars. English-language common name, e.g. 'Florida'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['The Sunshine State']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Success HTTP response code

`201 Created`

### Errors

See [Places: subdivisions - Errors](#subdivs_errors).
