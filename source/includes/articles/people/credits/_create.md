## <a name="person_credits_create"></a>Create a new person credit

> Request body | `POST /articles/people/satoru-iwata/credits`

```JSON
{
  "data": {
    "type": "person_credits",
    "attributes": {
      "category": "creative",
      "role": "Executive Producer"
    },
    "relationships": {
      "game": {
        "data": {
          "id": "46",
          "type": "games"
        }
      },
      "version": {
        "data": {
          "id": "1",
          "type": "game_versions"
        }
      },
      "place": {
        "data": {
          "id": "",
          "type": "places"
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
        "id": "1",
        "type": "person_credits",
        "attributes": {
            "category": "creative",
            "role": "Executive Producer"
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
                "data": null
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
        }
    ],
    "meta": {
        "keywords": "The Wonderful 101, Satoru Iwata, Executive Producer, person, credit, dbljump, video games, pc games, gaming",
        "description": "Find staff and company credits for The Wonderful 101 at Dbljump, the video game reference.",
        "created_at": "2017-06-29T15:25:57.428Z",
        "updated_at": "2017-06-29T15:25:57.428Z"
    }
}
```

Create a new game credit for a given person. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/people/{person-slug}/credits` (replace `person-slug` with the person record slug or ID)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | The credit category. Must be an accepted value.
role | string | Y | The credit, e.g. 'Director' or 'Lead Programmer'. Max 100 chars.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
game | belongs_to | Y | games | The game the credit relates to.
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

`201 Created`
