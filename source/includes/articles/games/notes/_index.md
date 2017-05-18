## Get all of a game's titles

> Response body | `HTTP 200`

```JSON
# GET /articles/games/the-wonderful-101/notes?page[size]=2

{
  "data": [
    {
      "id": "12",
      "type": "game_notes",
      "attributes": {
        "category": "Development",
        "body": "Was originally intended to feature an all-star cast of Nintendo characters.",
        "cite_url": "https://www.unseen64.net/2014/10/24/wiiu-the-wonderful-101-beta-development",
        "cite_title": "The Wonderful 101 [Beta / Concept – Wii U]",
        "cite_website": "Unseen64"
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
        "version": {
          "data": null,
          "links": {
            "related": "http://localhost:3000/articles/game_versions/2"
          }
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "created_bies"
          },
          "links": {
            "related": "http://localhost:3000/users/1"
          }
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

Retrieve all of a given game's notes. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{game-slug}/notes` (replace `{game-slug}` with parent game record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[game_notes]=body`
filter[{field}] | All records | Filter search by field, e.g. `?filter[category]=Development`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
