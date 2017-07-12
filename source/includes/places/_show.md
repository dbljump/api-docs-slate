## <a name="places_show"></a>Get single place

> Response body | `HTTP 200`

```JSON
# GET /places/united-states

{
    "data": {
        "id": "220",
        "type": "places",
        "attributes": {
            "kind": "country",
            "slug": "united-states",
            "name": "United States",
            "formatted": "United States",
            "short_name": "USA",
            "also_known_as": [],
            "latitude": 38,
            "longitude": -97,
            "iso_code": "US"
        },
        "relationships": {
            "parent": {
                "data": null,
                "links": {
                    "related": "http://api.dbljump.com/places/niue"
                }
            },
            "children": {
                "data": [
                    {
                        "id": "329",
                        "type": "places"
                    },
                    {
                        "id": "335",
                        "type": "places"
                    },
                    {
                        "id": "398",
                        "type": "places"
                    },
                    {
                        "id": "460",
                        "type": "places"
                    },
                    {
                        "id": "461",
                        "type": "places"
                    },
                    {
                        "id": "463",
                        "type": "places"
                    },
                    {
                        "id": "464",
                        "type": "places"
                    },
                    {
                        "id": "465",
                        "type": "places"
                    },
                    {
                        "id": "708",
                        "type": "places"
                    },
                    {
                        "id": "842",
                        "type": "places"
                    },
                    {
                        "id": "849",
                        "type": "places"
                    },
                    {
                        "id": "902",
                        "type": "places"
                    },
                    {
                        "id": "925",
                        "type": "places"
                    },
                    {
                        "id": "1047",
                        "type": "places"
                    },
                    {
                        "id": "1092",
                        "type": "places"
                    },
                    {
                        "id": "1146",
                        "type": "places"
                    },
                    {
                        "id": "1205",
                        "type": "places"
                    },
                    {
                        "id": "1258",
                        "type": "places"
                    },
                    {
                        "id": "1265",
                        "type": "places"
                    },
                    {
                        "id": "1274",
                        "type": "places"
                    },
                    {
                        "id": "1278",
                        "type": "places"
                    },
                    {
                        "id": "1363",
                        "type": "places"
                    },
                    {
                        "id": "1402",
                        "type": "places"
                    },
                    {
                        "id": "1574",
                        "type": "places"
                    },
                    {
                        "id": "1613",
                        "type": "places"
                    },
                    {
                        "id": "1665",
                        "type": "places"
                    },
                    {
                        "id": "1673",
                        "type": "places"
                    },
                    {
                        "id": "1714",
                        "type": "places"
                    },
                    {
                        "id": "1726",
                        "type": "places"
                    },
                    {
                        "id": "1733",
                        "type": "places"
                    },
                    {
                        "id": "1734",
                        "type": "places"
                    },
                    {
                        "id": "1752",
                        "type": "places"
                    },
                    {
                        "id": "1826",
                        "type": "places"
                    },
                    {
                        "id": "1833",
                        "type": "places"
                    },
                    {
                        "id": "1836",
                        "type": "places"
                    },
                    {
                        "id": "1838",
                        "type": "places"
                    },
                    {
                        "id": "1839",
                        "type": "places"
                    },
                    {
                        "id": "1843",
                        "type": "places"
                    },
                    {
                        "id": "1898",
                        "type": "places"
                    },
                    {
                        "id": "1901",
                        "type": "places"
                    },
                    {
                        "id": "1927",
                        "type": "places"
                    },
                    {
                        "id": "1979",
                        "type": "places"
                    },
                    {
                        "id": "1984",
                        "type": "places"
                    },
                    {
                        "id": "2001",
                        "type": "places"
                    },
                    {
                        "id": "2072",
                        "type": "places"
                    },
                    {
                        "id": "2139",
                        "type": "places"
                    },
                    {
                        "id": "2197",
                        "type": "places"
                    },
                    {
                        "id": "2463",
                        "type": "places"
                    },
                    {
                        "id": "2466",
                        "type": "places"
                    },
                    {
                        "id": "2595",
                        "type": "places"
                    },
                    {
                        "id": "2599",
                        "type": "places"
                    },
                    {
                        "id": "2676",
                        "type": "places"
                    },
                    {
                        "id": "2688",
                        "type": "places"
                    },
                    {
                        "id": "2727",
                        "type": "places"
                    },
                    {
                        "id": "2749",
                        "type": "places"
                    },
                    {
                        "id": "2750",
                        "type": "places"
                    },
                    {
                        "id": "2772",
                        "type": "places"
                    },
                    {
                        "id": "2801",
                        "type": "places"
                    },
                    {
                        "id": "2808",
                        "type": "places"
                    },
                    {
                        "id": "2812",
                        "type": "places"
                    }
                ],
                "links": {
                    "related": "http://api.dbljump.com/places/united-states/children"
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
                    "related": "http://api.dbljump.com/places/united-states/regions"
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
            "self": "http://api.dbljump.com/places/united-states"
        },
        "meta": {
            "description": "Find video game companies and games industry professionals from United States at Dbljump.",
            "keywords": "United States, USA, US, American, country, place, dbljump, video games, pc games, gaming",
            "created_at": "2017-07-12T13:28:33.331Z",
            "updated_at": "2017-07-12T13:28:33.331Z"
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

Retrieve a single place record. Places are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/{slug}` (replace `{slug}` with place record slug)

### Success HTTP response code

`200 OK`

### <a name="place_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
kind | string | Y | The place classification. Either 'region', 'country', 'subdivision', or 'locality'.
slug | string | Y | A record ID based on the formatted name, e.g. 'glasgow-scotland-united-kingdom'.
name | string | Y | The place name, e.g. 'Glasow' or 'Scotland' or 'United Kingdom' or 'Europe'.
formatted | string | Y | The full name including parent places, e.g. 'Glasgow, Scotland, United Kingdom'.
short_name | string | | A commonly-used short name, e.g. 'USA', 'UK', 'CA', 'LA'.
also_known_as | array | | An array of aliases, e.g. `['Nippon', '日本']` for Japan.
latitude | number | | Geographic coordinate.
longitude | number | | Geographic coordinate.
iso_code | string | Countries only | 2-character ISO 3166-1 code. Countries only.

### Relationships

Name | Record type | Relationship type | Description
---- | ---------- | ------------------ | -----------
created_by | users | belongs_to | The user that created the record.
parent | places | belongs_to | The country a subdivision is in; he subdivision a locality is in; null for countries and regions.
children | places | has_many | The countries inside a region; the subdivisions inside a country; the localities inside a subdivision; null for localities.
regions | places | has_many | The regions that a country, subdivision, or locality belong to. Null for regions.

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
