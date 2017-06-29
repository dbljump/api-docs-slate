## <a name="person_credits_show"></a>Get a single person credit

> Response body | `HTTP 200`

```JSON
# GET /articles/person_credits/1

{
    "data": {
        "id": "1",
        "type": "person_credits",
        "attributes": {
            "category": "special",
            "role": "Special Thanks"
        },
        "relationships": {
            "credited": {
                "data": {
                    "id": "26",
                    "type": "people"
                },
                "links": {
                    "related": "http://localhost:3000/articles/people/satoru-iwata"
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
                "data": {
                    "id": "55",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/czechia"
                }
            }
        }
    },
    "included": [
        {
            "id": "26",
            "type": "people",
            "attributes": {
                "display_title": "Satoru Iwata"
            },
            "links": {
                "self": "http://localhost:3000/articles/people/satoru-iwata"
            }
        },
        {
            "id": "46",
            "type": "games",
            "attributes": {
                "display_title": "The Wonderful 101"
            },
            "links": {
                "self": "http://localhost:3000/articles/games/the-wonderful-101"
            }
        },
        {
            "id": "55",
            "type": "places",
            "attributes": {
                "formatted": "Czechia"
            },
            "links": {
                "self": "http://localhost:3000/places/czechia"
            }
        }
    ],
    "meta": {
        "keywords": "The Wonderful 101, Satoru Iwata, Special Thanks, Czechia, person, credit, dbljump, video games, pc games, gaming",
        "description": "Find staff and company credits for The Wonderful 101 at Dbljump, the video game reference.",
        "created_at": "2017-06-29T15:25:57.428Z",
        "updated_at": "2017-06-29T15:42:21.047Z"
    }
}
```

Retrieve a single person credit. Game credits are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/person_credits/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`

### <a name="person_notes_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | The credit category.
role | string | Y | The credit, e.g. 'Director' or 'Lead Programmer'.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
credited | people | belongs_to
game | games | belongs_to
version | game_versions | belongs_to
place | places | belongs_to

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
