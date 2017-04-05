## <a name="subdivs_update"></a>Update a subdivision record

> Request body

```JSON
{
  "data": {
    "type": "places",
    "id": "north-puerto-rico",
    "attributes": {
      "country_id": "10",
      "name": "Updated Subdivision",
      "also_known_as": ["Updated Subdiv", "Changed Subdiv"],
      "latitude": "3.0",
      "longitude": "-25.00"
    }
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "269",
    "type": "places",
    "attributes": {
      "subtype": "subdivisions",
      "slug": "updated-subdivision-armenia",
      "name": "Updated Subdivision",
      "short_name": null,
      "formatted": "Updated Subdivision, Armenia",
      "latitude": 3,
      "longitude": -25,
      "also_known_as": [
        "Updated Subdiv",
        "Changed Subdiv"
      ]
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
          "id": "10",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/countries/armenia"
        }
      },
      "localities": {
        "links": {
          "related": "http://api.dbljump.com/places/subdivisions/updated-subdivision-armenia/localities"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/subdivisions/updated-subdivision-armenia"
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
      "id": "10",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "armenia",
        "name": "Armenia",
        "short_name": null,
        "formatted": "Armenia"
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/armenia"
      }
    }
  ],
  "meta": {
    "keywords": "updated subdivision, armenia, updated subdiv, changed subdiv, state, county, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Updated Subdivision, Armenia at Dbljump.",
    "created_at": "2017-03-30T12:38:30.707Z",
    "updated_at": "2017-03-30T13:46:24.805Z"
  }
}
```

Update an existing subdivision record. The user must be an admin.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /places/subdivisions/{slug}` (replace `{slug}` with subdivision record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
country_id | integer | Y | ID of parent country.
name | string | Y | 2-250 chars. English-language common name, e.g. 'Florida'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['The Sunshine State']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Success HTTP response code

`200 OK`
