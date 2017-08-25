## Search genres

> Response body | `HTTP 200`

```JSON
# GET /search/genres?q=action&sort=name&page[number]=1&page[size]=3&fields[genres]=name,short_name&filter[created_by_id]=1

{
    "data": [
        {
            "id": "1",
            "type": "genres",
            "attributes": {
                "name": "action",
                "short_name": ""
            },
            "links": {
                "self": "http://localhost:3000/genres/action"
            },
            "meta": {
                "created_at": "2017-08-25T08:33:05.290Z",
                "updated_at": "2017-08-25T08:33:05.290Z",
                "meta_description": "Find action-genre games at Dbljump, the video game reference.",
                "meta_keywords": "action, genre, dbljump, video games, pc games, gaming",
                "total_games": 14
            }
        },
        {
            "id": "58",
            "type": "genres",
            "attributes": {
                "name": "action RPG",
                "short_name": ""
            },
            "links": {
                "self": "http://localhost:3000/genres/action-rpg"
            },
            "meta": {
                "created_at": "2017-08-25T08:33:05.863Z",
                "updated_at": "2017-08-25T08:33:05.863Z",
                "meta_description": "Find action RPG-genre games at Dbljump, the video game reference.",
                "meta_keywords": "action RPG, genre, dbljump, video games, pc games, gaming",
                "total_games": 0
            }
        },
        {
            "id": "3",
            "type": "genres",
            "attributes": {
                "name": "art",
                "short_name": ""
            },
            "links": {
                "self": "http://localhost:3000/genres/art"
            },
            "meta": {
                "created_at": "2017-08-25T08:33:05.305Z",
                "updated_at": "2017-08-25T08:33:05.305Z",
                "meta_description": "Find art-genre games at Dbljump, the video game reference.",
                "meta_keywords": "art, genre, dbljump, video games, pc games, gaming",
                "total_games": 0
            }
        }
    ],
    "links": {
        "self": "http://localhost:3000/search/genres?fields%5Bgenres%5D=name%2Cshort_name&filter%5Bcreated_by_id%5D=1&page%5Bnumber%5D=1&page%5Bsize%5D=3&q=action&sort=name",
        "next": "http://localhost:3000/search/genres?fields%5Bgenres%5D=name%2Cshort_name&filter%5Bcreated_by_id%5D=1&page%5Bnumber%5D=2&page%5Bsize%5D=3&q=action&sort=name",
        "last": "http://localhost:3000/search/genres?fields%5Bgenres%5D=name%2Cshort_name&filter%5Bcreated_by_id%5D=1&page%5Bnumber%5D=4&page%5Bsize%5D=3&q=action&sort=name"
    },
    "meta": {
        "total_items": 10
    }
}
```

Search genres. Automatically paginated.

* User authentication: required
* Authorization level: any

### HTTP request

`GET /search/genres?q={search_string}`

### Success HTTP response code

`200 OK`
