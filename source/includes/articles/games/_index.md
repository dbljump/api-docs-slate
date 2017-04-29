## Get all games

> Response body | `HTTP 200`

```JSON
# GET /articles/games?page[size]=2

{
  "data": [
    {
      "id": "45",
      "type": "games",
      "attributes": {
        "display_title": "Pong",
        "description": "Pong is a table tennis sports game and is one of the earliest arcade video games.",
        "release_date": "1972-11-29",
        "release_year": 1972,
        "slug": "pong"
      },
      "relationships": {
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://localhost:3000/users/1"
          }
        }
      },
      "links": {
        "self": "http://localhost:3000/articles/games/pong"
      }
    },
    {
      "id": "46",
      "type": "games",
      "attributes": {
        "display_title": "The Wonderful 101",
        "description": "The Wonderful 101 is an action-adventure video game developed by Platinum Games for the Nintendo Wii U.",
        "release_date": "2013-08-23",
        "release_year": 2013,
        "slug": "the-wonderful-101"
      },
      "relationships": {
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://localhost:3000/users/1"
          }
        }
      },
      "links": {
        "self": "http://localhost:3000/articles/games/the-wonderful-101"
      }
    }
  ],
  "links": {
    "self": "http://localhost:3000/articles/games?page%5Bnumber%5D=1&page%5Bsize%5D=2",
    "next": "http://localhost:3000/articles/games?page%5Bnumber%5D=2&page%5Bsize%5D=2",
    "last": "http://localhost:3000/articles/games?page%5Bnumber%5D=2&page%5Bsize%5D=2"
  },
  "meta": {
    "total_items": 3
  }
}
```

Retrieve all game articles. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[games]=display_title,release_date`
filter[{field}] | All records | Filter search by field, e.g. `?filter[release_year]=2015`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
