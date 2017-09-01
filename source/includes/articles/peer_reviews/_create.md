## <a name="peer_reviews_create"></a>Submit an article for review

> Request body | `POST /articles/peer_reviews`

```JSON
{
  "data": {
    "type": "peer_reviews",
    "attributes": {
      "article_id": "1"
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
    "data": {
        "id": "1",
        "type": "companies",
        "attributes": {
            "display_title": "Nintendo Co., Ltd.",
            "description": "Nintendo is a Japanese video game hardware and software company founded in 1889.",
            "slug": "nintendo-co-ltd",
            "last_submitted_at": "2017-06-21T16:15:23.948Z",
            "last_reviewed_at": null,
            "last_review_outcome": null,
            "last_review_comments": null,
            "published_at": null,
            "status": "submitted",
            "origin_date": null,
            "origin_year": 1889,
            "end": null,
            "end_date": null,
            "end_year": null
        },
        "relationships": {
            "primary_image": {
                "data": null
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
            "origin_place": {
                "data": {
                    "id": "2932",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
                }
            },
            "latest_place": {
                "data": null
            },
            "names": {
                "data": [
                    {
                        "id": "1",
                        "type": "company_names"
                    },
                    {
                        "id": "2",
                        "type": "company_names"
                    },
                    {
                        "id": "3",
                        "type": "company_names"
                    },
                    {
                        "id": "4",
                        "type": "company_names"
                    },
                    {
                        "id": "5",
                        "type": "company_names"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/nintendo-co-ltd/names"
                }
            },
            "notes": {
                "data": [
                    {
                        "id": "1",
                        "type": "company_notes"
                    },
                    {
                        "id": "2",
                        "type": "company_notes"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/nintendo-co-ltd/notes"
                }
            },
            "images": {
                "data": [
                    {
                        "id": "1",
                        "type": "images"
                    },
                    {
                        "id": "2",
                        "type": "images"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/nintendo-co-ltd/images"
                }
            },
            "credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/companies/nintendo-co-ltd/credits"
                }
            },
            "parents": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/companies/nintendo-co-ltd/parents"
                }
            },
            "children": {
                "data": [
                    {
                        "id": "5",
                        "type": "company_kinships"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/nintendo-co-ltd/children"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/articles/companies/nintendo-co-ltd"
        }
    },
    "meta": {
        "keywords": "Nintendo Co., Ltd., 1889, Kyoto, Kyoto Prefecture, Japan, 任天堂株式会社, Nintendō Kabushiki gaisha, Nintendo Playing Card Co., Nintendo Koppai, Nintendo, company, profile, biography, trivia, dbljump, video games, pc games, gaming",
        "description": "Find Nintendo Co., Ltd.'s game credits, profile, images and facts at Dbljump, the video game reference.",
        "created_at": "2017-06-20T23:07:11.468Z",
        "updated_at": "2017-06-21T16:15:24.482Z"
    }
}
```

Submit a game, company, or person article for peer review. The user must be the creator of the article.

* User authentication: required
* Authorization level: editor or admin; user must be article creator

### HTTP request

`POST /articles/peer_reviews`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
article_id | integer | Y | The article record ID

### Success HTTP response code

`200 OK`
