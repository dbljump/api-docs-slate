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
        "id": "2939",
        "type": "places",
        "attributes": {
            "kind": "subdivision",
            "slug": "maryland-united-states",
            "name": "Maryland",
            "formatted": "Maryland, United States",
            "short_name": "MD",
            "also_known_as": [
                "Old Line State",
                "Chesapeake Bay State"
            ],
            "latitude": 38,
            "longitude": -77,
            "iso_code": ""
        },
        "relationships": {
            "parent": {
                "data": {
                    "id": "220",
                    "type": "places"
                },
                "links": {
                    "related": "http://api.dbljump.com/places/united-states"
                }
            },
            "children": {
                "data": [],
                "links": {
                    "related": "http://api.dbljump.com/places/maryland-united-states/children"
                }
            },
            "regions": {
                "data": [
                    {
                        "id": "238",
                        "type": "places"
                    },
                    {
                        "id": "233",
                        "type": "places"
                    }
                ],
                "links": {
                    "related": "http://api.dbljump.com/places/maryland-united-states/regions"
                }
            },
            "created_by": {
                "data": {
                    "id": "2",
                    "type": "users"
                },
                "links": {
                    "related": "http://api.dbljump.com/users/2"
                }
            }
        },
        "links": {
            "self": "http://api.dbljump.com/places/maryland-united-states"
        },
        "meta": {
            "description": "Find video game companies and games industry professionals from Maryland, United States at Dbljump.",
            "keywords": "Maryland, United States, MD, Old Line State, Chesapeake Bay State, state, county, place, dbljump, video games, pc games, gaming",
            "created_at": "2017-07-12T13:54:03.802Z",
            "updated_at": "2017-07-12T13:54:03.802Z"
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
                "avatar": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1707121330.jpg"
            },
            "links": {
                "self": "http://api.dbljump.com/users/2"
            },
            "meta": {
                "description": "Neil Wheatley is a member at Dbljump, the video game reference.",
                "keywords": "neil, Neil Wheatley, user, dbljump, video games, pc games, gaming",
                "last_signed_in_at": "2017-07-12T13:48:47.195Z",
                "last_sign_in_ip": "86.12.129.15",
                "sign_in_count": 2,
                "activated_at": "2017-07-12T13:30:02.955Z",
                "created_at": "2017-07-12T13:30:03.831Z",
                "updated_at": "2017-07-12T13:48:47.255Z"
            }
        }
    ]
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
