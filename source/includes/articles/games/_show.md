## <a name="games_show"></a>Get a single game

> Response body | `HTTP 200`

```JSON
# GET /articles/games/the-wonderful-101

{
    "data": {
        "id": "46",
        "type": "games",
        "attributes": {
            "display_title": "The Wonderful 101",
            "description": "The Wonderful 101 is an action-adventure video game developed by Platinum Games for the Nintendo Wii U.",
            "slug": "the-wonderful-101",
            "last_submitted_at": null,
            "last_reviewed_at": null,
            "last_review_outcome": null,
            "last_review_comments": null,
            "published_at": "2017-06-28T17:04:28.473Z",
            "status": "published",
            "release_date": "2013-08-23",
            "release_year": 2013
        },
        "relationships": {
            "primary_image": {
                "data": null,
                "links": {
                    "related": "http://localhost:3000/media/images/nintendo-office-photo"
                }
            },
            "created_by": {
                "data": {
                    "id": "1",
                    "type": "users"
                },
                "links": {
                    "related": "http://localhost:3000/users/1"
                }
            },
            "last_reviewed_by": {
                "data": null
            },
            "titles": {
                "data": [
                    {
                        "id": "58",
                        "type": "game_titles"
                    },
                    {
                        "id": "59",
                        "type": "game_titles"
                    },
                    {
                        "id": "60",
                        "type": "game_titles"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/games/the-wonderful-101/titles"
                }
            },
            "notes": {
                "data": [
                    {
                        "id": "12",
                        "type": "game_notes"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/games/the-wonderful-101/notes"
                }
            },
            "genres": {
                "data": [
                    {
                        "id": "1",
                        "type": "genres"
                    },
                    {
                        "id": "2",
                        "type": "genres"
                    },
                    {
                        "id": "23",
                        "type": "genres"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/games/the-wonderful-101/genres"
                }
            },
            "versions": {
                "data": [
                    {
                        "id": "1",
                        "type": "game_versions"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/games/the-wonderful-101/versions"
                }
            },
            "images": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/the-wonderful-101/images"
                }
            },
            "company_credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/the-wonderful-101/company_credits"
                }
            },
            "person_credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/the-wonderful-101/company_credits"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/articles/games/the-wonderful-101"
        }
    },
    "included": [
        {
            "id": "1",
            "type": "users",
            "attributes": {
                "username": "tikithekiwi",
                "avatar": null
            },
            "links": {
                "self": "http://localhost:3000/users/1"
            }
        },
        {
            "id": "1",
            "type": "genres",
            "attributes": {
                "name": "action",
                "short_name": ""
            },
            "links": {
                "self": "http://localhost:3000/genres/action"
            }
        },
        {
            "id": "2",
            "type": "genres",
            "attributes": {
                "name": "adventure",
                "short_name": ""
            },
            "links": {
                "self": "http://localhost:3000/genres/adventure"
            }
        },
        {
            "id": "23",
            "type": "genres",
            "attributes": {
                "name": "comedy",
                "short_name": ""
            },
            "links": {
                "self": "http://localhost:3000/genres/comedy"
            }
        }
    ],
    "meta": {
        "keywords": "The Wonderful 101, 2013, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
        "description": "Find The Wonderful 101 trivia, screenshots, credits and other info at Dbljump, the video game reference.",
        "created_at": "2017-06-28T17:04:28.478Z",
        "updated_at": "2017-06-28T17:04:28.478Z"
    }
}
```

Retrieve a single game article. Games are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{slug}` (replace `{slug}` with record slug)

### Success HTTP response code

`200 OK`

### <a name="person_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | The article title, usually the company name.
description | text | | A short biography up to 800 chars.
release_date | date | | Between 1st Jan 1800 and the present.
release_year | integer | | Between 1800 and the present year.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
created_by | users | belongs_to
genres | genres | has_many
primary_image | images | belongs_to

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar
genres | genres | name, short_name
images | primary_image | title, file

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
