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
            "also_known_as": [
                "'United States of America'"
            ],
            "latitude": 38,
            "longitude": -97,
            "iso_code": "US"
        },
        "relationships": {
            "parent": {
                "data": null
            },
            "children": {
                "data": [
                    {
                        "id": "2734",
                        "type": "places"
                    },
                    {
                        "id": "2733",
                        "type": "places"
                    },
                    {
                        "id": "2732",
                        "type": "places"
                    },
                    {
                        "id": "2731",
                        "type": "places"
                    },
                    {
                        "id": "2730",
                        "type": "places"
                    },
                    {
                        "id": "2729",
                        "type": "places"
                    },
                    {
                        "id": "2728",
                        "type": "places"
                    },
                    {
                        "id": "2727",
                        "type": "places"
                    },
                    {
                        "id": "2726",
                        "type": "places"
                    },
                    {
                        "id": "2725",
                        "type": "places"
                    },
                    {
                        "id": "2724",
                        "type": "places"
                    },
                    {
                        "id": "2723",
                        "type": "places"
                    },
                    {
                        "id": "2722",
                        "type": "places"
                    },
                    {
                        "id": "2721",
                        "type": "places"
                    },
                    {
                        "id": "2720",
                        "type": "places"
                    },
                    {
                        "id": "2719",
                        "type": "places"
                    },
                    {
                        "id": "2718",
                        "type": "places"
                    },
                    {
                        "id": "2717",
                        "type": "places"
                    },
                    {
                        "id": "2716",
                        "type": "places"
                    },
                    {
                        "id": "2715",
                        "type": "places"
                    },
                    {
                        "id": "2714",
                        "type": "places"
                    },
                    {
                        "id": "2713",
                        "type": "places"
                    },
                    {
                        "id": "2712",
                        "type": "places"
                    },
                    {
                        "id": "2711",
                        "type": "places"
                    },
                    {
                        "id": "2710",
                        "type": "places"
                    },
                    {
                        "id": "2709",
                        "type": "places"
                    },
                    {
                        "id": "2708",
                        "type": "places"
                    },
                    {
                        "id": "2707",
                        "type": "places"
                    },
                    {
                        "id": "2706",
                        "type": "places"
                    },
                    {
                        "id": "2705",
                        "type": "places"
                    },
                    {
                        "id": "2704",
                        "type": "places"
                    },
                    {
                        "id": "2703",
                        "type": "places"
                    },
                    {
                        "id": "2702",
                        "type": "places"
                    },
                    {
                        "id": "2701",
                        "type": "places"
                    },
                    {
                        "id": "2700",
                        "type": "places"
                    },
                    {
                        "id": "2699",
                        "type": "places"
                    },
                    {
                        "id": "2698",
                        "type": "places"
                    },
                    {
                        "id": "2697",
                        "type": "places"
                    },
                    {
                        "id": "2696",
                        "type": "places"
                    },
                    {
                        "id": "2695",
                        "type": "places"
                    },
                    {
                        "id": "2694",
                        "type": "places"
                    },
                    {
                        "id": "2693",
                        "type": "places"
                    },
                    {
                        "id": "2692",
                        "type": "places"
                    },
                    {
                        "id": "2691",
                        "type": "places"
                    },
                    {
                        "id": "2690",
                        "type": "places"
                    },
                    {
                        "id": "2689",
                        "type": "places"
                    },
                    {
                        "id": "2688",
                        "type": "places"
                    },
                    {
                        "id": "2687",
                        "type": "places"
                    },
                    {
                        "id": "2686",
                        "type": "places"
                    },
                    {
                        "id": "2685",
                        "type": "places"
                    },
                    {
                        "id": "2684",
                        "type": "places"
                    },
                    {
                        "id": "2683",
                        "type": "places"
                    },
                    {
                        "id": "2682",
                        "type": "places"
                    },
                    {
                        "id": "2681",
                        "type": "places"
                    },
                    {
                        "id": "2680",
                        "type": "places"
                    },
                    {
                        "id": "2679",
                        "type": "places"
                    },
                    {
                        "id": "2678",
                        "type": "places"
                    },
                    {
                        "id": "2677",
                        "type": "places"
                    },
                    {
                        "id": "2676",
                        "type": "places"
                    },
                    {
                        "id": "2675",
                        "type": "places"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/places/220/children"
                },
                "meta": {
                    "total": 60
                }
            },
            "regions": {
                "data": [
                    {
                        "id": "240",
                        "type": "places"
                    },
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
                    "related": "http://localhost:3000/places/220/regions"
                },
                "meta": {
                    "total": 3
                }
            },
            "origin_articles": {
                "data": [
                    {
                        "id": "55",
                        "type": "people"
                    },
                    {
                        "id": "57",
                        "type": "people"
                    },
                    {
                        "id": "64",
                        "type": "people"
                    },
                    {
                        "id": "56",
                        "type": "people"
                    },
                    {
                        "id": "67",
                        "type": "people"
                    }
                ]
            },
            "latest_articles": {
                "data": []
            },
            "created_by": {
                "data": {
                    "id": "1",
                    "type": "users"
                },
                "links": {
                    "related": "http://localhost:3000/users/1"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/places/220"
        },
        "meta": {
            "created_at": "2017-08-25T08:31:18.461Z",
            "updated_at": "2017-08-25T08:31:18.461Z",
            "meta_description": "Find video game companies and games industry professionals from United States at Dbljump.",
            "meta_keywords": "United States, USA, 'United States of America', US, American, country, place, dbljump, video games, pc games, gaming",
            "total_children": 60,
            "total_regions": 3,
            "total_origin_articles": 5,
            "total_latest_articles": 0
        }
    }
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
origin_articles | polymorphic | has_many | Companies founded or people born in this place.
latest_articles | polymorphic | has_many | Companies HQ'd or people who died in this place.

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
