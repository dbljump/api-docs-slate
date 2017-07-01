## <a name="company_credits_update"></a>Update a company credit

> Request body | `PATCH /articles/company_credits/3`

```JSON
{
  "data": {
    "type": "company_credits",
    "id": "3",
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
        "id": "3",
        "type": "company_credits",
        "attributes": {
            "category": "special",
            "role": "Special Thanks"
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
        "keywords": "The Wonderful 101, Nintendo Co., Ltd., Special Thanks, Czechia, company, credit, dbljump, video games, pc games, gaming",
        "description": "Find staff and company credits for The Wonderful 101 at Dbljump, the video game reference.",
        "created_at": "2017-06-30T23:23:15.317Z",
        "updated_at": "2017-06-30T23:55:47.337Z"
    }
}
```

Update an existing company credit. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/company_notes/{id}` (replace `{id}` with record ID)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
category | string | Y | The credit category. Must be an accepted value.
role | string | Y | The credit, e.g. 'Publisher' or 'Developer'.

### Relationships

Check this section's code example to see how to update these relationships.

NOTE - The game and credited relationships cannot be updated.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
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

`200 OK`
