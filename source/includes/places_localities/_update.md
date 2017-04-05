## <a name="localities_update"></a>Update a locality record

> Request body

```JSON
{
  "data": {
    "type": "places",
    "id": "matsumoto-nagano-prefecture-japan",
    "attributes": {
      "name": "Updated City",
      "also_known_as": ["Updated City", "Changed Locality"],
      "latitude": "24.0",
      "longitude": "89.5"
    },
    "relationships": {
      "subdivision": {
        "data": {
          "id": "1001",
          "type": "places"
        }
      }
    }
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "2936",
    "type": "places",
    "attributes": {
      "subtype": "localities",
      "slug": "updated-city-epirus-greece",
      "name": "Updated City",
      "short_name": null,
      "formatted": "Updated City, Epirus, Greece",
      "also_known_as": [
        "Updated City",
        "Changed Locality"
      ],
      "latitude": 24,
      "longitude": 89.5
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
          "id": "78",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/countries/greece"
        }
      },
      "subdivision": {
        "data": {
          "id": "1001",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/subdivisions/epirus-greece"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/localities/updated-city-epirus-greece"
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
      "id": "78",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "greece",
        "name": "Greece",
        "short_name": null,
        "formatted": "Greece"
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/greece"
      }
    },
    {
      "id": "1001",
      "type": "places",
      "attributes": {
        "subtype": "subdivisions",
        "slug": "epirus-greece",
        "name": "Epirus",
        "short_name": null,
        "formatted": "Epirus, Greece"
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/epirus-greece"
      }
    }
  ],
  "meta": {
    "keywords": "updated city, epirus, greece, updated city, changed locality, city, town, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Updated City, Epirus, Greece at Dbljump.",
    "created_at": "2017-03-30T12:40:07.612Z",
    "updated_at": "2017-03-30T13:51:05.564Z"
  }
}
```

Update an existing locality record. The user must be an admin.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /places/localities/{slug}` (replace `{slug}` with locality record slug)

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
name | string | Y | 2-250 chars. English-language common name, e.g. 'Los Angeles'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['LA', 'City of Angels']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | ----------
subdivision | belongs_to | Y | places | The [subdivision](#subdivs_intro) this locality is in.

### Success HTTP response code

`200 OK`
