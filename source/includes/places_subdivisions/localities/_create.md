## Subdivision localities: create new

> Request body

```JSON
{
  "data": {
    "type": "places",
    "attributes": {
      "name": "New City",
      "also_known_as": ["That New City", "The New Locality"],
      "latitude": "70.3",
      "longitude": "-45.5"
    }
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "2941",
    "type": "places",
    "attributes": {
      "subtype": "localities",
      "slug": "new-city-tokyo-prefecture-japan",
      "name": "New City",
      "short_name": null,
      "formatted": "New City, Tokyo Prefecture, Japan",
      "also_known_as": [
        "That New City",
        "The New Locality"
      ],
      "latitude": 70.3,
      "longitude": -45.5
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
          "id": "102",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/countries/japan"
        }
      },
      "subdivision": {
        "data": {
          "id": "2627",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/subdivisions/tokyo-prefecture-japan"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/localities/new-city-tokyo-prefecture-japan"
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
      "id": "2627",
      "type": "places",
      "attributes": {
        "subtype": "subdivisions",
        "slug": "tokyo-prefecture-japan",
        "name": "Tokyo Prefecture",
        "short_name": null,
        "formatted": "Tokyo Prefecture, Japan"
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/tokyo-prefecture-japan"
      }
    }
  ],
  "meta": {
    "keywords": "new city, tokyo prefecture, japan, that new city, the new locality, city, town, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from New City, Tokyo Prefecture, Japan at Dbljump.",
    "created_at": "2017-03-30T13:57:23.909Z",
    "updated_at": "2017-03-30T13:57:23.909Z"
  }
}
```

Create a new locality record belonging to the given subdivision. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /places/subdivisions/{subdivision-slug}/localities` (replace `{subdivision-slug}` with subdivision record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | 2-250 chars. English-language common name, e.g. 'Los Angeles'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['LA', 'City of Angels']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Success HTTP response code

`201 Created`

### Errors

See [Places:localities - Errors](#localities_errors).
