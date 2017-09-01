## <a name="peer_reviews_update"></a>Review an unpublished article

> Request body | `PATCH /articles/peer_reviews/1`

```JSON
{
  "data": {
    "type": "peer_reviews",
    "id": "1",
    "attributes": {
      "last_review_outcome": "fail_style",
      "last_review_comments": "Please fix typing errors."
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
            "last_reviewed_at": "2017-06-21T16:21:15.946Z",
            "last_review_outcome": "fail_style",
            "last_review_comments": "Please fix typing errors.",
            "published_at": null,
            "status": "draft",
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
                "data": {
                    "id": "2",
                    "type": "users"
                },
                "links": {
                    "related": "http://localhost:3000/users/2"
                }
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
        "updated_at": "2017-06-21T16:21:16.184Z"
    }
}
```

Record the outcome of an article peer review. The user must be an editor, and must not be the article creator.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/peer_reviews/{ID}` (replace `{ID}` with article ID)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
last_review_outcome | string | Y | Must be `ok`, `fail_style`, `fail_incomplete`, or `fail_accuracy`
last_review_comments | text | Y | Reviewer feedback on submission. 1-800 characters.

### Success HTTP response code

`200 OK`
