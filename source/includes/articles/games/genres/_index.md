## Game genres: get all

> Response body | `HTTP 200`

```JSON
# GET /articles/games/dark-souls/genres

{
  "data": [
    {
      "id": "1",
      "type": "genres",
      "attributes": {
        "name": "action",
        "short_name": "",
        "also_known_as": [],
        "slug": "action"
      },
      "relationships": {
        "parent": {
          "data": null
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
      },
      "links": {
        "self": "http://localhost:3000/genres/action"
      }
    },
    {
      "id": "12",
      "type": "genres",
      "attributes": {
        "name": "role-playing game",
        "short_name": "RPG",
        "also_known_as": [],
        "slug": "role-playing-game"
      },
      "relationships": {
        "parent": {
          "data": null
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
      },
      "links": {
        "self": "http://localhost:3000/genres/role-playing-game"
      }
    },
    {
      "id": "20",
      "type": "genres",
      "attributes": {
        "name": "fantasy",
        "short_name": "",
        "also_known_as": [],
        "slug": "fantasy"
      },
      "relationships": {
        "parent": {
          "data": null
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
      },
      "links": {
        "self": "http://localhost:3000/genres/fantasy"
      }
    }
  ],
  "links": {},
  "meta": {
    "total_items": 3
  }
}
```

Retrieve all genres belonging to a given game. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{game_slug}/genres` (replace `{game_slug}` with game record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[genres]=name,short_name`
filter[{field}] | All records | Filter search by field, e.g. `?filter[name]=action`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
