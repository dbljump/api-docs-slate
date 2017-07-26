## Get all game versions

> Response body | `HTTP 200`

```JSON
# GET /articles/games/dark-souls/versions?page[size]=2

{
  "data": [
    {
      "id": "2",
      "type": "game_versions",
      "attributes": {
        "status": "extant",
        "target_fps": null,
        "resolution_w": null,
        "resolution_h: null
      },
      "relationships": {
        "game": {
          "data": {
            "id": "47",
            "type": "games"
          },
          "links": {
            "related": "http://localhost:3000/articles/games/dark-souls"
          }
        },
        "platform": {
          "data": {
            "id": "3",
            "type": "platforms"
          },
          "links": {
            "related": "http://localhost:3000/platforms/sony-playstation-3"
          }
        }
      }
    },
    {
      "id": "3",
      "type": "game_versions",
      "attributes": {
        "status": "extant",
        "target_fps": null,
        "resolution_w": null,
        "resolution_h: null
      },
      "relationships": {
        "game": {
          "data": {
            "id": "47",
            "type": "games"
          },
          "links": {
            "related": "http://localhost:3000/articles/games/dark-souls"
          }
        },
        "platform": {
          "data": {
            "id": "8",
            "type": "platforms"
          },
          "links": {
            "related": "http://localhost:3000/platforms/microsoft-xbox-360"
          }
        }
      }
    }
  ],
  "links": {
    "self": "http://localhost:3000/articles/games/dark-souls/versions?page%5Bnumber%5D=1&page%5Bsize%5D=2",
    "next": "http://localhost:3000/articles/games/dark-souls/versions?page%5Bnumber%5D=2&page%5Bsize%5D=2",
    "last": "http://localhost:3000/articles/games/dark-souls/versions?page%5Bnumber%5D=2&page%5Bsize%5D=2"
  },
  "meta": {
    "total_items": 3
  }
}
```

Retrieve all game versions. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{game-slug}/versions`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[game_versions]=status,target_fps`
filter[{field}] | All records | Filter search by field, e.g. `?filter[status]=rumored`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
