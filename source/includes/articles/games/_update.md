## <a name="games_update"></a>Update a game

> Request body | `PATCH /articles/games/dark-souls`

```JSON
{
  "data": {
    "type": "games",
    "id": "pong",
    "attributes": {
      "display_title": "Changed Name",
      "description": "Updated description for an updated article.",
      "release_date": "1995-11-17",
      "release_year": ""
    },
    "relationships": {
      "primary_image": {
        "data": {
          "id": "1",
          "type": "images"
        }
      },
      "genres": {
        "data": [
          { "type": "genres", "id": "5" },
          { "type": "genres", "id": "12" }
        ]
      }
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
    "data": {
        "id": "47",
        "type": "games",
        "attributes": {
            "display_title": "Changed Name",
            "description": "Updated description for an updated article.",
            "slug": "changed-name-4e0f8184-9d0a-43c4-93aa-fac630f602f4",
            "last_submitted_at": null,
            "last_reviewed_at": null,
            "last_review_outcome": null,
            "last_review_comments": null,
            "published_at": "2017-06-22T13:51:23.881Z",
            "status": "published",
            "release_date": "1995-11-17",
            "release_year": 1995
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
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/changed-name-4e0f8184-9d0a-43c4-93aa-fac630f602f4/titles"
                }
            },
            "notes": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/changed-name-4e0f8184-9d0a-43c4-93aa-fac630f602f4/notes"
                }
            },
            "genres": {
                "data": [
                    {
                        "id": "12",
                        "type": "genres"
                    },
                    {
                        "id": "5",
                        "type": "genres"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/games/changed-name-4e0f8184-9d0a-43c4-93aa-fac630f602f4/genres"
                }
            },
            "versions": {
                "data": [
                    {
                        "id": "2",
                        "type": "game_versions"
                    },
                    {
                        "id": "3",
                        "type": "game_versions"
                    },
                    {
                        "id": "4",
                        "type": "game_versions"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/games/changed-name-4e0f8184-9d0a-43c4-93aa-fac630f602f4/versions"
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
                    "related": "http://localhost:3000/articles/games/changed-name-4e0f8184-9d0a-43c4-93aa-fac630f602f4/images"
                }
            },
            "company_credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/changed-name-4e0f8184-9d0a-43c4-93aa-fac630f602f4/company_credits"
                }
            },
            "person_credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/games/changed-name-4e0f8184-9d0a-43c4-93aa-fac630f602f4/company_credits"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/articles/games/changed-name-4e0f8184-9d0a-43c4-93aa-fac630f602f4"
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
            "id": "12",
            "type": "genres",
            "attributes": {
                "name": "role-playing game",
                "short_name": "RPG"
            },
            "links": {
                "self": "http://localhost:3000/genres/role-playing-game"
            }
        },
        {
            "id": "5",
            "type": "genres",
            "attributes": {
                "name": "educational",
                "short_name": ""
            },
            "links": {
                "self": "http://localhost:3000/genres/educational"
            }
        }
    ],
    "meta": {
        "keywords": "Changed Name, 1995, PlayStation 3, Xbox 360, Windows, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
        "description": "Find Changed Name trivia, screenshots, credits and other info at Dbljump, the video game reference.",
        "created_at": "2017-06-22T13:51:23.885Z",
        "updated_at": "2017-06-22T15:52:04.565Z"
    }
}
```

Update an existing game article. The user must be an editor. The genres relationship can be edited.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/games/{slug}` (replace `{slug}` with record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | 1-250 characters.
description | text | | 1-800 characters.
release_date | date | | Between 1st Jan 1800 and the present.
release_year | integer | | Between 1800 and the present year.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
primary_image | belongs_to | | images | The main article image, usually a game poster.
genres | has_many | | genres | The genres this game belongs to.

### Success HTTP response code

`200 OK`
