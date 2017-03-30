## <a name="subdivs_create"></a>Create a new subdivision record

> Request body

```JSON
{
  "data": {
    "type": "places",
    "attributes": {
      "country_id": "1",
      "name": "New Subdivision",
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
    "id": "2938",
    "type": "places",
    "attributes": {
      "subtype": "subdivisions",
      "slug": "new-subdivision-afghanistan",
      "name": "New Subdivision",
      "short_name": null,
      "formatted": "New Subdivision, Afghanistan",
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
          "related": "http://api.dbljump.com/places/subdivisions/new-subdivision-afghanistan/localities"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/subdivisions/new-subdivision-afghanistan"
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
        "avatar": {
          "url": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1703301240.jpg"
        }
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
    "keywords": "new subdivision, afghanistan, that new subdiv, the new subdiv, state, county, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from New Subdivision, Afghanistan at Dbljump.",
    "created_at": "2017-03-30T13:45:33.826Z",
    "updated_at": "2017-03-30T13:45:33.826Z"
  }
}
```

Create a new subdivision record. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /places/subdivisions`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
country_id | integer | Y | ID of parent country.
name | string | Y | 2-250 chars. English-language common name, e.g. 'Florida'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['The Sunshine State']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Success HTTP response code

`201 Created`
