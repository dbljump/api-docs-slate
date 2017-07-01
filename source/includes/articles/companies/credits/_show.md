## <a name="company_credits_show"></a>Get a single company credit

> Response body | `HTTP 200`

```JSON
# GET /articles/company_credits/1

{
    "data": {
        "id": "4",
        "type": "company_credits",
        "attributes": {
            "category": "development",
            "role": "Developer"
        },
        "relationships": {
            "credited": {
                "data": {
                    "id": "1",
                    "type": "companies"
                },
                "links": {
                    "related": "http://localhost:3000/articles/companies/nintendo-co-ltd"
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
                "data": null
            }
        }
    },
    "included": [
        {
            "id": "1",
            "type": "companies",
            "attributes": {
                "display_title": "Nintendo Co., Ltd."
            },
            "links": {
                "self": "http://localhost:3000/articles/companies/nintendo-co-ltd"
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
        }
    ],
    "meta": {
        "keywords": "The Wonderful 101, Nintendo Co., Ltd., Developer, company, credit, dbljump, video games, pc games, gaming",
        "description": "Find staff and company credits for The Wonderful 101 at Dbljump, the video game reference.",
        "created_at": "2017-06-30T23:44:17.051Z",
        "updated_at": "2017-06-30T23:44:17.051Z"
    }
}
```

Retrieve a single company credit. Game credits are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/company_credits/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`

### <a name="company_credits_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | The credit category.
role | string | Y | The credit, e.g. 'Publisher' or 'Developer'.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
credited | companies | belongs_to
game | games | belongs_to
version | game_versions | belongs_to
place | places | belongs_to

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
