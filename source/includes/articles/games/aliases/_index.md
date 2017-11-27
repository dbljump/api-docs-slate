## Get a collection of game aliases

> Response body | `HTTP 200`

```JSON
# GET /articles/game_aliases?page[size]=2

{
  "data": [
    {
      "id": "58",
      "type": "game_aliases",
      "attributes": {
        "display_text": "Project P-100",
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
      "type": "game_aliases",
      "attributes": {
        "display_text": "Za Wandafuru Wan Ō Wan",
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

Retrieve a collection of game aliases.

### HTTP request

`GET /articles/game_aliases`

### Success HTTP response code

`200 OK`
