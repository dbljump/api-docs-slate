## <a name="companies_show"></a>Get a single company

> Response body | `HTTP 200`

```JSON
# GET /articles/companies/nintendo-co-ltd

{
    "data": {
        "id": "8",
        "type": "companies",
        "attributes": {
            "display_title": "Nintendo Co., Ltd.",
            "sort_title": "Nintendo Co., Ltd.",
            "slug": "nintendo-co-ltd",
            "description": "Nintendo is a Japanese video game hardware and software company founded in 1889.",
            "last_review_outcome": null,
            "last_review_comments": null,
            "origin_date": null,
            "origin_year": 1889,
            "ended": null,
            "end_date": null,
            "end_year": null
        },
        "relationships": {
            "primary_image": {
                "data": {
                    "id": "17",
                    "type": "images"
                },
                "links": {
                    "related": "http://localhost:3000/media/images/17"
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
            "origin_place": {
                "data": {
                    "id": "2964",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/2964"
                }
            },
            "latest_place": {
                "data": null
            },
            "names": {
                "data": [
                    {
                        "id": "8",
                        "type": "company_names"
                    },
                    {
                        "id": "53",
                        "type": "company_names"
                    },
                    {
                        "id": "54",
                        "type": "company_names"
                    },
                    {
                        "id": "55",
                        "type": "company_names"
                    },
                    {
                        "id": "56",
                        "type": "company_names"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/8/names"
                },
                "meta": {
                    "total": 5
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
                    "related": "http://localhost:3000/articles/companies/8/notes"
                },
                "meta": {
                    "total": 2
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
                    },
                    {
                        "id": "3",
                        "type": "images"
                    },
                    {
                        "id": "4",
                        "type": "images"
                    },
                    {
                        "id": "5",
                        "type": "images"
                    },
                    {
                        "id": "17",
                        "type": "images"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/8/images"
                },
                "meta": {
                    "total": 6
                }
            },
            "credits": {
                "data": [
                    {
                        "id": "11",
                        "type": "company_credits"
                    },
                    {
                        "id": "33",
                        "type": "company_credits"
                    },
                    {
                        "id": "35",
                        "type": "company_credits"
                    },
                    {
                        "id": "39",
                        "type": "company_credits"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/8/credits"
                },
                "meta": {
                    "total": 4
                }
            },
            "parents": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/companies/8/parents"
                },
                "meta": {
                    "total": 0
                }
            },
            "children": {
                "data": [
                    {
                        "id": "12",
                        "type": "company_kinships"
                    },
                    {
                        "id": "28",
                        "type": "company_kinships"
                    },
                    {
                        "id": "29",
                        "type": "company_kinships"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/8/children"
                },
                "meta": {
                    "total": 3
                }
            },
            "platforms": {
                "data": [
                    {
                        "id": "24",
                        "type": "platforms"
                    },
                    {
                        "id": "25",
                        "type": "platforms"
                    },
                    {
                        "id": "26",
                        "type": "platforms"
                    },
                    {
                        "id": "27",
                        "type": "platforms"
                    },
                    {
                        "id": "28",
                        "type": "platforms"
                    },
                    {
                        "id": "29",
                        "type": "platforms"
                    },
                    {
                        "id": "30",
                        "type": "platforms"
                    },
                    {
                        "id": "31",
                        "type": "platforms"
                    },
                    {
                        "id": "32",
                        "type": "platforms"
                    },
                    {
                        "id": "33",
                        "type": "platforms"
                    },
                    {
                        "id": "34",
                        "type": "platforms"
                    },
                    {
                        "id": "35",
                        "type": "platforms"
                    },
                    {
                        "id": "36",
                        "type": "platforms"
                    },
                    {
                        "id": "37",
                        "type": "platforms"
                    },
                    {
                        "id": "38",
                        "type": "platforms"
                    },
                    {
                        "id": "39",
                        "type": "platforms"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/platforms?filter%5Bholder_id%5D=8"
                },
                "meta": {
                    "total": 16
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/articles/companies/8"
        },
        "meta": {
            "created_at": "2017-08-25T08:32:15.829Z",
            "updated_at": "2017-08-25T08:32:31.459Z",
            "meta_description": "Find Nintendo Co., Ltd.'s game credits, profile, images and facts at Dbljump, the video game reference.",
            "meta_keywords": "Nintendo Co., Ltd., 1889, Kyoto, Kyoto Prefecture, Japan, Nintendo, 任天堂株式会社, Nintendō Kabushiki gaisha, Nintendo Playing Card Co., Nintendo Koppai, company, profile, biography, trivia, dbljump, video games, pc games, gaming",
            "status": "published",
            "last_submitted_at": null,
            "last_reviewed_at": null,
            "published_at": "2017-08-25T08:32:15.798Z",
            "total_names": 5,
            "total_notes": 2,
            "total_images": 6,
            "total_credits": 4,
            "total_parents": 0,
            "total_children": 3
        }
    }
}
```

Retrieve a single company article. Companies are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/companies/{slug}` (replace `{slug}` with record slug)

### Success HTTP response code

`200 OK`

### <a name="company_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | The article title, usually the company name.
description | text | | A short biography up to 800 chars.
origin_date | date | | Between 1st Jan 1800 and the present.
origin_year | integer | | Between 1800 and the present year.
end | boolean | | True if the company has end.
end_date | date | | Between 1st Jan 1800 and the present.
end_year | integer | | Between 1800 and the present year.
slug | string | Y | A record ID based on the display_title.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
origin_place | places | belongs_to
latest_place | places | belongs_to
created_by | users | belongs_to
primary_image | images | belongs_to
platforms  | platforms  | has_many  

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
