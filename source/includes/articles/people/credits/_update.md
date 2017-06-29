## <a name="person_credits_update"></a>Update a person credit

> Request body | `PATCH /articles/person_credits/1`

```JSON
{
  "data": {
    "type": "person_credits",
    "attributes": {
      "category": "special",
      "role": "Special Thanks"
    },
    "relationships": {
      "version": {
        "data": {
          "id": "1",
          "type": "game_versions"
        }
      },
      "place": {
        "data": {
          "id": "55",
          "type": "places"
        }
      }
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
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

Update an existing person credit. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/person_notes/{id}` (replace `{id}` with record ID)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | The credit category. Must be an accepted value.
role | string | Y | The credit, e.g. 'Director' or 'Lead Programmer'.

### Relationships

Check this section's code example to see how to update these relationships.

NOTE - The game relationship cannot be updated.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
version | belongs_to | | game_versions | The game version the credit relates to (optional).
place | belongs_to | | places | The place the credit relates to (optional).

### <a name="person_credit_categories"></a>Person credit categories

The following are accepted value for the categories attribute:

* creative
* development
* technology
* visuals
* sound
* language
* special
* misc

### Success HTTP response code

`200 OK`
