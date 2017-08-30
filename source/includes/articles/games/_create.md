## <a name="games_create"></a>Create a new game

> Request body | `POST /articles/games`

```JSON
{
  "data": {
    "type": "games",
    "attributes": {
      "display_title": "New Game",
      "description": "New Game is an action game developed by some company or other.",
      "origin_date": "2015-01-03",
      "origin_year": ""
    },
    "relationships": {
      "primary_image": {
        "data": {
          "id": "1",
          "type": "images"
        }
      }
    }
  }
}
```

> Response body | `HTTP 201`

```JSON
{
    "data": {
        "id": "50",
        "type": "games",
        "attributes": {
            "display_title": "New Game",
            "description": "New Game is an action game developed by some company or other.",
            "slug": "new-game",
            "last_submitted_at": null,
            "last_reviewed_at": null,
            "last_review_outcome": null,
            "last_review_comments": null,
            "published_at": null,
            "status": "draft",
            "origin_date": "2015-01-03",
            "origin_year": 2015
        },
        "relationships": {
            "primary_image": {
                "data": {
                    "id": "1",
                    "type": "images"
                },
                "links": {
                    "related": "http://localhost:3000/media/images/nintendo-office-photo"
                }
            },
            "created_by": {
                "data": {
                    "id": "2",
                    "type": "users"
                },
                "links": {
                    "related": "http://localhost:3000/users/2"
                }
            },
            "last_reviewed_by": {
                "data": null
            },
            "titles": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/new-game/titles"
                }
            },
            "notes": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/new-game/notes"
                }
            },
            "genres": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/new-game/genres"
                }
            },
            "versions": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/new-game/versions"
                }
            },
            "images": {
                "data": [
                    {
                        "id": "1",
                        "type": "images"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/games/new-game/images"
                }
            },
            "company_credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/new-game/company_credits"
                }
            },
            "person_credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/new-game/company_credits"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/articles/games/new-game"
        }
    },
    "included": [
        {
            "id": "1",
            "type": "images",
            "attributes": {
                "file": "http://localhost:3000/uploads/images/1/nintendo-hq-kyoto-2006.jpg",
                "title": "Nintendo office"
            },
            "links": {
                "self": "http://localhost:3000/media/images/nintendo-office-photo"
            }
        },
        {
            "id": "2",
            "type": "users",
            "attributes": {
                "username": "neil",
                "avatar": "http://localhost:3000/uploads/user_avatar/2/1706221451.jpg"
            },
            "links": {
                "self": "http://localhost:3000/users/2"
            }
        }
    ],
    "meta": {
        "keywords": "New Game, 2015, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
        "description": "Find New Game trivia, screenshots, credits and other info at Dbljump, the video game reference.",
        "created_at": "2017-06-27T22:31:20.875Z",
        "updated_at": "2017-06-27T22:31:20.875Z"
    }
}
```

Create a new game article. User must be an editor or admin. The genres relationship cannot be edited.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/games`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | 1-250 characters.
description | text | | 1-800 characters.
origin_date | date | | Between 1st Jan 1800 and the present.
origin_year | integer | | Between 1800 and the present year.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
primary_image | belongs_to | | images | The main article image, usually a game poster.

### Success HTTP response code

`201 Created`
