## Get all of a version's releases

> Response body | `HTTP 200`

```JSON
# GET /articles/game_version_releases

{
    "data": [
        {
            "id": "1",
            "type": "version_releases",
            "attributes": {
                "date": "2013-08-23",
                "year": 2013,
                "physical": true,
                "digital": true
            },
            "relationships": {
                "version": {
                    "data": {
                        "id": "1",
                        "type": "game_versions"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/game_versions/1"
                    }
                },
                "place": {
                    "data": {
                        "id": "234",
                        "type": "places"
                    },
                    "links": {
                        "related": "http://localhost:3000/places/europe"
                    }
                }
            }
        },
        {
            "id": "2",
            "type": "version_releases",
            "attributes": {
                "date": "2013-09-15",
                "year": 2013,
                "physical": true,
                "digital": true
            },
            "relationships": {
                "version": {
                    "data": {
                        "id": "1",
                        "type": "game_versions"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/game_versions/1"
                    }
                },
                "place": {
                    "data": {
                        "id": "233",
                        "type": "places"
                    },
                    "links": {
                        "related": "http://localhost:3000/places/north-america"
                    }
                }
            }
        },
        {
            "id": "3",
            "type": "version_releases",
            "attributes": {
                "date": "2013-08-24",
                "year": 2013,
                "physical": true,
                "digital": true
            },
            "relationships": {
                "version": {
                    "data": {
                        "id": "1",
                        "type": "game_versions"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/game_versions/1"
                    }
                },
                "place": {
                    "data": {
                        "id": "102",
                        "type": "places"
                    },
                    "links": {
                        "related": "http://localhost:3000/places/japan"
                    }
                }
            }
        }
    ],
    "links": {},
    "meta": {
        "total_items": 3
    }
}
```

Retrieve all game version releases. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/game_version_releases`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[version_releases]=date,year`
filter[{field}] | All records | Filter search by field, e.g. `?filter[year]=2013`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
