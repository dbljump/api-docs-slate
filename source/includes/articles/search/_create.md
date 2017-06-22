## <a name="articles_search_create"></a>Run a search

> Request body | `POST /articles/search?page[size]=3`

```JSON
{
  "data": {
    "type": "article_searches",
    "attributes": {
      "search": "japanese"
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
    "data": [
        {
            "id": "1",
            "type": "companies",
            "attributes": {
                "display_title": "Nintendo Co., Ltd.",
                "description": "Nintendo is a Japanese video game hardware and software company founded in 1889."
            },
            "links": {
                "self": "http://localhost:3000/articles/companies/nintendo-co-ltd"
            }
        },
        {
            "id": "2",
            "type": "companies",
            "attributes": {
                "display_title": "Sega Games Co., Ltd.",
                "description": "SEGA is a Japanese video game software and hardware maker founded in 1940."
            },
            "links": {
                "self": "http://localhost:3000/articles/companies/sega-games-co-ltd"
            }
        },
        {
            "id": "3",
            "type": "companies",
            "attributes": {
                "display_title": "Sony Corporation",
                "description": "Sony is a Japanese corporation and holder of the PlayStation gaming platforms."
            },
            "links": {
                "self": "http://localhost:3000/articles/companies/sony-corporation"
            }
        }
    ],
    "links": {
        "self": "http://localhost:3000/articles/search?page%5Bnumber%5D=1&page%5Bsize%5D=3",
        "next": "http://localhost:3000/articles/search?page%5Bnumber%5D=2&page%5Bsize%5D=3",
        "last": "http://localhost:3000/articles/search?page%5Bnumber%5D=5&page%5Bsize%5D=3"
    },
    "meta": {
        "total_items": 13
    }
}
```

Search for game, company and person articles that match the given search string. Automatically paginated.

* User authentication: not required

### HTTP request

`POST /articles/search`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
search | string | Y | The search string.

### Response attributes

The return collection includes limited record attributes, suitable for display on a search results page.

Attribute | Type | description
--------- | ---- | -----------
display_title | string | The name of the game, company or person.
description | text | The article summary.
primary_image | relationship | The article's main image, e.g. a game poster, company logo or person likeness.

### Success HTTP response code

`200 OK`
