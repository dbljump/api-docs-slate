## Get all of a game's company-credits

> Response body | `HTTP 200`

```JSON
# GET /articles/games/the-wonderful-101/company_credits?page[size]=2

{
    "data": [
        {
            "id": "3",
            "type": "company_credits",
            "attributes": {
                "category": "publishing",
                "role": "Publisher"
            },
            "relationships": {
                "credited": {
                    "data": {
                        "id": "1",
                        "type": "companies"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/companies/nintendo-co-ltd"
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

Retrieve all of a given game's company credits. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{game-slug}/company_credits` (replace `{game-slug}` with parent game record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[company_credits]=role`
filter[{field}] | All records | Filter search by field, e.g. `?filter[category]=development`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
