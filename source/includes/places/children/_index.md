## <a name="places_children_index"></a>Get all place children

> Response body | `HTTP 200`

```JSON
# GET /places/united-states/children?page[size]=3

{
    "data": [
        {
            "id": "329",
            "type": "places",
            "attributes": {
                "kind": "subdivision",
                "slug": "alabama-united-states",
                "name": "Alabama",
                "formatted": "Alabama, United States",
                "short_name": null,
                "also_known_as": [],
                "latitude": 32.3182314,
                "longitude": -86.902298,
                "iso_code": null
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
                        "related": "http://api.dbljump.com/places/alabama-united-states/children"
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
                        "related": "http://api.dbljump.com/places/alabama-united-states/regions"
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
                "self": "http://api.dbljump.com/places/alabama-united-states"
            },
            "meta": {
                "description": "Find video game companies and games industry professionals from Alabama, United States at Dbljump.",
                "keywords": "Alabama, United States, state, county, place, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-12T13:28:36.800Z",
                "updated_at": "2017-07-12T13:28:36.800Z"
            }
        },
        {
            "id": "335",
            "type": "places",
            "attributes": {
                "kind": "subdivision",
                "slug": "alaska-united-states",
                "name": "Alaska",
                "formatted": "Alaska, United States",
                "short_name": null,
                "also_known_as": [],
                "latitude": 64.2008413,
                "longitude": -149.4936733,
                "iso_code": null
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
                        "related": "http://api.dbljump.com/places/alaska-united-states/children"
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
                        "related": "http://api.dbljump.com/places/alaska-united-states/regions"
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
                "self": "http://api.dbljump.com/places/alaska-united-states"
            },
            "meta": {
                "description": "Find video game companies and games industry professionals from Alaska, United States at Dbljump.",
                "keywords": "Alaska, United States, state, county, place, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-12T13:28:36.924Z",
                "updated_at": "2017-07-12T13:28:36.924Z"
            }
        },
        {
            "id": "398",
            "type": "places",
            "attributes": {
                "kind": "subdivision",
                "slug": "american-samoa-united-states",
                "name": "American Samoa",
                "formatted": "American Samoa, United States",
                "short_name": null,
                "also_known_as": [],
                "latitude": 21.3239718,
                "longitude": -157.876498,
                "iso_code": null
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
                        "related": "http://api.dbljump.com/places/american-samoa-united-states/children"
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
                        "related": "http://api.dbljump.com/places/american-samoa-united-states/regions"
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
                "self": "http://api.dbljump.com/places/american-samoa-united-states"
            },
            "meta": {
                "description": "Find video game companies and games industry professionals from American Samoa, United States at Dbljump.",
                "keywords": "American Samoa, United States, state, county, place, dbljump, video games, pc games, gaming",
                "created_at": "2017-07-12T13:28:39.075Z",
                "updated_at": "2017-07-12T13:28:39.075Z"
            }
        }
    ],
    "links": {
        "self": "http://api.dbljump.com/places/united-states/children?page%5Bnumber%5D=1&page%5Bsize%5D=3",
        "next": "http://api.dbljump.com/places/united-states/children?page%5Bnumber%5D=2&page%5Bsize%5D=3",
        "last": "http://api.dbljump.com/places/united-states/children?page%5Bnumber%5D=20&page%5Bsize%5D=3"
    },
    "meta": {
        "total_items": 60
    }
}
```

Retrieve all places that belong to a given places, i.e. countries that belong to a region; subdivisions that belong to a country; and localities that belong to a subdivision. Returns a `404` error for localities, which do not have children. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/{place-slug}/children`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[places]=name,formatted`
filter[{field}] | All records | Filter search by field, e.g. `?filter[name]=Tokyo Prefecture`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
