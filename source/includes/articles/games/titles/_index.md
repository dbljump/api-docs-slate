## Get all of a game's titles

> Response body | `HTTP 200`

```JSON
# GET /articles/games/the-wonderful-101/titles?page[size]=2

{
  "data": [
    {
      "id": "58",
      "type": "game_titles",
      "attributes": {
        "title": "Project P-100",
        "kind": "working",
        "writing_system": "Latin"
      },
      "relationships": {
        "game": {
          "data": {
            "id": "46",
            "type": "games"
          },
          "links": {
            "related": "http://localhost:3000/articles/games/the-wonderful-101"
          }
        },
        "place": {
          "data": null
        },
        "version": {
          "data": null
        }
      }
    },
    {
      "id": "59",
      "type": "game_titles",
      "attributes": {
        "title": "Za Wandafuru Wan Ō Wan",
        "kind": "title",
        "writing_system": "Latin"
      },
      "relationships": {
        "game": {
          "data": {
            "id": "46",
            "type": "games"
          },
          "links": {
            "related": "http://localhost:3000/articles/games/the-wonderful-101"
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
        },
        "version": {
          "data": null
        }
      }
    }
  ],
  "links": {
    "self": "http://localhost:3000/articles/games/the-wonderful-101/titles?page%5Bnumber%5D=1&page%5Bsize%5D=2",
    "next": "http://localhost:3000/articles/games/the-wonderful-101/titles?page%5Bnumber%5D=2&page%5Bsize%5D=2",
    "last": "http://localhost:3000/articles/games/the-wonderful-101/titles?page%5Bnumber%5D=2&page%5Bsize%5D=2"
  },
  "meta": {
    "total_items": 3
  }
}
```

Retrieve all of a given game's titles. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{game-slug}/titles` (replace `{game-slug}` with parent game record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[company_names]=title`
filter[{field}] | All records | Filter search by field, e.g. `?filter[kind]=working`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
