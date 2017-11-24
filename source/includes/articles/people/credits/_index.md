## Get all person credits

> Response body | `HTTP 200`

```JSON
# GET /articles/person_credits

{
    "data": [
        {
            "id": "1",
            "type": "person_credits",
            "attributes": {
                "category": "creative",
                "role": "Executive Producer"
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
                    "data": null
                }
            }
        }
    ],
    "links": {},
    "meta": {
        "total_items": 1
    }
}
```

Retrieve all person-game credits. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/person_credits`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[person_credits]=role`
filter[{field}] | All records | Filter search by field, e.g. `?filter[category]=creative`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
