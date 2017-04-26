## Get all people

> Response body | `HTTP 200`

```JSON
# GET /articles/people?page[size]=3

{
  "data": [
    {
      "id": "44",
      "type": "people",
      "attributes": {
        "display_title": "Hideki Kamiya",
        "description": "Hideki Kamiya is a game designer and director known for his work with Capcom and as a co-founder of PlatinumGames.",
        "gender": "male",
        "birth_date": "1970-12-19",
        "birth_year": 1970,
        "dead": null,
        "death_date": null,
        "death_year": null,
        "slug": "hideki-kamiya"
      },
      "relationships": {
        "birth_place": {
          "data": {
            "id": "2936",
            "type": "places"
          },
          "links": {
            "related": "http://localhost:3000/places/matsumoto-nagano-prefecture-japan"
          }
        },
        "death_place": {
          "data": null
        },
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
        "self": "http://localhost:3000/articles/people/hideki-kamiya"
      }
    },
    {
      "id": "43",
      "type": "people",
      "attributes": {
        "display_title": "Corrinne Yu",
        "description": "Corrinne Yu is an American game programmer known for her work on the Halo series, with Sony development studio Naughty Dog, and with Amazon.",
        "gender": "female",
        "birth_date": null,
        "birth_year": null,
        "dead": null,
        "death_date": null,
        "death_year": null,
        "slug": "corrinne-yu"
      },
      "relationships": {
        "birth_place": {
          "data": {
            "id": "90",
            "type": "places"
          },
          "links": {
            "related": "http://localhost:3000/places/hong-kong"
          }
        },
        "death_place": {
          "data": null
        },
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
        "self": "http://localhost:3000/articles/people/corrinne-yu"
      }
    },
    {
      "id": "42",
      "type": "people",
      "attributes": {
        "display_title": "Tim Sweeney",
        "description": "Tim Sweeney is an American game programmer and the founder of Epic Games. He is best known for his work on the Unreal Engine.",
        "gender": "male",
        "birth_date": null,
        "birth_year": 1970,
        "dead": null,
        "death_date": null,
        "death_year": null,
        "slug": "tim-sweeney"
      },
      "relationships": {
        "birth_place": {
          "data": {
            "id": "2890",
            "type": "places"
          },
          "links": {
            "related": "http://localhost:3000/places/potomac-maryland-united-states"
          }
        },
        "death_place": {
          "data": null
        },
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
        "self": "http://localhost:3000/articles/people/tim-sweeney"
      }
    }
  ],
  "links": {
    "self": "http://localhost:3000/articles/people?page%5Bnumber%5D=1&page%5Bsize%5D=3",
    "next": "http://localhost:3000/articles/people?page%5Bnumber%5D=2&page%5Bsize%5D=3",
    "last": "http://localhost:3000/articles/people?page%5Bnumber%5D=8&page%5Bsize%5D=3"
  },
  "meta": {
    "total_items": 24
  }
}
```

Retrieve all people articles. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/people`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[people]=display_name,description`
filter[{field}] | All records | Filter search by field, e.g. `?filter[gender]=female`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
