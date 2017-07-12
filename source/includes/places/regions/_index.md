## <a name="places_regions_index"></a>Get all place regions

> Response body | `HTTP 200`

```JSON
# GET /places/united-states/regions

{
    "data": [
        {
            "id": "238",
            "type": "places",
            "attributes": {
                "kind": "region",
                "slug": "us-and-canada",
                "name": "US and Canada",
                "formatted": "US and Canada",
                "short_name": "US&Ca",
                "also_known_as": [],
                "latitude": null,
                "longitude": null,
                "iso_code": null
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
                            "id": "36",
                            "type": "places"
                        },
                        {
                            "id": "220",
                            "type": "places"
                        }
                    ],
                    "links": {
                        "related": "http://api.dbljump.com/places/us-and-canada/children"
                    }
                },
                "regions": {
                    "data": null,
                    "links": {
                        "related": "http://api.dbljump.com/places/us-and-canada/regions"
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
                "self": "http://api.dbljump.com/places/us-and-canada"
            },
            "meta": {
                "description": "Find video game companies and games industry professionals from US and Canada at Dbljump.",
                "keywords": "US and Canada, US&Ca, place, geography, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-12T13:28:33.735Z",
                "updated_at": "2017-07-12T13:28:33.735Z"
            }
        },
        {
            "id": "233",
            "type": "places",
            "attributes": {
                "kind": "region",
                "slug": "north-america",
                "name": "North America",
                "formatted": "North America",
                "short_name": "NA",
                "also_known_as": [],
                "latitude": null,
                "longitude": null,
                "iso_code": null
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
                            "id": "36",
                            "type": "places"
                        },
                        {
                            "id": "133",
                            "type": "places"
                        },
                        {
                            "id": "220",
                            "type": "places"
                        }
                    ],
                    "links": {
                        "related": "http://api.dbljump.com/places/north-america/children"
                    }
                },
                "regions": {
                    "data": null,
                    "links": {
                        "related": "http://api.dbljump.com/places/north-america/regions"
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
                "self": "http://api.dbljump.com/places/north-america"
            },
            "meta": {
                "description": "Find video game companies and games industry professionals from North America at Dbljump.",
                "keywords": "North America, NA, place, geography, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-12T13:28:33.636Z",
                "updated_at": "2017-07-12T13:28:33.636Z"
            }
        }
    ],
    "links": {},
    "meta": {
        "total_items": 2
    }
}
```

Retrieve all regions that a given country belongs to. Returns a `404` error for regions, subdivision, and localities. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/{place-slug}/regions`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[places]=formatted`
filter[{field}] | All records | Filter search by field, e.g. `?filter[name]=Asia`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
