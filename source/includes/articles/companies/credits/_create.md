## <a name="company_credits_create"></a>Create a new company credit

> Request body | `POST /articles/company_credits`

```JSON
{
  "data": {
    "type": "company_credits",
    "attributes": {
      "category": "development",
      "role": "Developer"
    },
    "relationships": {
      "credited": {
        "data": {
          "id": "1",
          "type": "games"
        }
      },
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

Create a new game credit for a given company. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/company_credits`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | The credit category. Must be an accepted value.
role | string | Y | The credit, e.g. 'Publisher' or 'Developr'. Max 100 chars.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
credited | belongs_to | Y |  companies | The company credited.
game | belongs_to | Y | games | The game the credit relates to.
version | belongs_to | | game_versions | The game version the credit relates to (optional).
place | belongs_to | | places | The place the credit relates to (optional).

### <a name="company_credit_categories"></a>Company credit categories

The following are accepted value for the categories attribute:

* publishing
* development
* technology
* visuals
* sound
* language
* special
* misc

### Success HTTP response code

`201 Created`
