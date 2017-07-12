## <a name="places_update"></a>Update a place record

> Request body | `PATCH /places/europe`

```JSON
{
  "data": {
    "type": "places",
    "id": "europe",
    "attributes": {
      "name": "New Name",
      "short_name": "Short",
      "also_known_as": ["Edited Region", "Renamed Region"],
      "latitude": "54.5",
      "longitude": "15.3"
    },
    "relationships": {
      "children": {
        "data": [
          { "type": "places", "id": "219" },
          { "type": "places", "id": "71" },
          { "type": "places", "id": "75" }
        ]
      }
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
    "data": {
        "id": "234",
        "type": "places",
        "attributes": {
            "kind": "region",
            "slug": "new-name",
            "name": "New Name",
            "formatted": "New Name",
            "short_name": "Short",
            "also_known_as": [
                "Edited Region",
                "Renamed Region"
            ],
            "latitude": 54.5,
            "longitude": 15.3,
            "iso_code": null
        },
        "relationships": {
            "parent": {
                "data": null,
                "links": {
                    "related": "http://api.dbljump.com/places/united-states"
                }
            },
            "children": {
                "data": [
                    {
                        "id": "71",
                        "type": "places"
                    },
                    {
                        "id": "75",
                        "type": "places"
                    },
                    {
                        "id": "219",
                        "type": "places"
                    }
                ],
                "links": {
                    "related": "http://api.dbljump.com/places/new-name/children"
                }
            },
            "regions": {
                "data": null,
                "links": {
                    "related": "http://api.dbljump.com/places/new-name/regions"
                }
            },
            "created_by": {
                "data": {
                    "id": "1",
                    "type": "users"
                },
                "links": {
                    "related": "http://api.dbljump.com/users/1"
                }
            }
        },
        "links": {
            "self": "http://api.dbljump.com/places/new-name"
        },
        "meta": {
            "description": "Find video game companies and games industry professionals from New Name at Dbljump.",
            "keywords": "New Name, Short, Edited Region, Renamed Region, place, geography, dbljump, video games, pc games, gaming",
            "created_at": "2017-07-12T13:28:33.655Z",
            "updated_at": "2017-07-12T13:57:30.480Z"
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
            },
            "meta": {
                "description": "Tiki the Kiwi is a member at Dbljump, the video game reference.",
                "keywords": "tikithekiwi, Tiki the Kiwi, user, dbljump, video games, pc games, gaming",
                "last_signed_in_at": null,
                "last_sign_in_ip": null,
                "sign_in_count": 0,
                "activated_at": "2017-07-12T13:28:27.875Z",
                "created_at": "2017-07-12T13:28:27.985Z",
                "updated_at": "2017-07-12T13:28:27.985Z"
            }
        }
    ]
}
```

Update an existing place record. The user must be an admin, except for `locality` records that were created by the current user. The `kind` attribute cannot be changed.

* User authentication: required
* Authorization level: admin, except for `locality` records that were created by the current user.

### HTTP request

`PATCH /places/{slug}` (replace `{slug}` with place record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | Unique. 2-250 chars. English-language common name, e.g. 'United States'.
short_name | string | | Unique. 2-20 chars. Common short name, e.g. 'USA'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['US', 'America']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.
iso_code | string | Country-only | Unique. 2 chars. ISO 3166-1 country code.

### Relationships

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | ----------
parent | belongs_to | Subdivisions and localities only | places | The country a subdivision is in; the subdivision a locality is in.
children | has_many | | places | The countries inside a region.

### Success HTTP response code

`200 OK`
