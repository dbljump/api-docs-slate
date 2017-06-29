## Get all of a game's person-credits

> Response body | `HTTP 200`

```JSON
# GET /articles/games/the-wonderful-101/person_credits?page[size]=2

{
    "data": [
        {
            "id": "1",
            "type": "person_credits",
            "attributes": {
                "category": "special",
                "role": "Special Thanks"
            },
            "relationships": {
                "credited": {
                    "data": {
                        "id": "26",
                        "type": "people"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/people/satoru-iwata"
                    }
                },
                "game": {
                    "data": {
                        "id": "46",
                        "type": "games"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/games/the-wonderful-101"
                    }
                },
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
                        "id": "55",
                        "type": "places"
                    },
                    "links": {
                        "related": "http://localhost:3000/places/czechia"
                    }
                }
            }
        },
        {
            "id": "2",
            "type": "person_credits",
            "attributes": {
                "category": "creative",
                "role": "Executive Producer"
            },
            "relationships": {
                "credited": {
                    "data": {
                        "id": "21",
                        "type": "people"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/people/shigeru-miyamoto"
                    }
                },
                "game": {
                    "data": {
                        "id": "46",
                        "type": "games"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/games/the-wonderful-101"
                    }
                },
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
                    "data": null,
                    "links": {
                        "related": "http://localhost:3000/places/czechia"
                    }
                }
            }
        }
    ],
    "links": {},
    "meta": {
        "total_items": 2
    }
}
```

Retrieve all of a given game's person credits. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{game-slug}/person_credits` (replace `{game-slug}` with parent game record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[person_credits]=role`
filter[{field}] | All records | Filter search by field, e.g. `?filter[category]=creative`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
