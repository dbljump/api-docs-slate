## <a name="comanies_create"></a>Create a new company

> Request body | `POST /articles/companies`

```JSON
{
  "data": {
    "type": "companies",
    "attributes": {
      "display_title": "New Firm",
      "description": "New Firm is a new company, and this describes it.",
      "origin_date": "1965-09-12",
      "origin_year": "",
      "end": "",
      "end_date": "2012-05-18",
      "end_year": ""
    },
    "relationships": {
      "primary_image": {
        "data": {
          "id": "1",
          "type": "images"
        }
      },
      "origin_place": {
        "data": {
          "id": "2883",
          "type": "places"
        }
      },
      "latest_place": {
        "data": {
          "id": "2932",
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
        "id": "49",
        "type": "companies",
        "attributes": {
            "display_title": "New Firm",
            "description": "New Firm is a new company, and this describes it.",
            "slug": "new-firm",
            "last_submitted_at": null,
            "last_reviewed_at": null,
            "last_review_outcome": null,
            "last_review_comments": null,
            "published_at": null,
            "status": "draft",
            "origin_date": "1965-09-12",
            "origin_year": 1965,
            "end": true,
            "end_date": "2012-05-18",
            "end_year": 2012
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
            "origin_place": {
                "data": {
                    "id": "2883",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/los-angeles-california-united-states"
                }
            },
            "latest_place": {
                "data": {
                    "id": "2932",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
                }
            },
            "names": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/companies/new-firm/names"
                }
            },
            "notes": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/companies/new-firm/notes"
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
                    "related": "http://localhost:3000/articles/companies/new-firm/images"
                }
            },
            "credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/companies/new-firm/credits"
                }
            },
            "parents": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/companies/new-firm/parents"
                }
            },
            "children": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/companies/new-firm/children"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/articles/companies/new-firm"
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
        },
        {
            "id": "2883",
            "type": "places",
            "attributes": {
                "name": "Los Angeles",
                "formatted": "Los Angeles, California, United States"
            },
            "links": {
                "self": "http://localhost:3000/places/los-angeles-california-united-states"
            }
        },
        {
            "id": "2932",
            "type": "places",
            "attributes": {
                "name": "Kyoto",
                "formatted": "Kyoto, Kyoto Prefecture, Japan"
            },
            "links": {
                "self": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
            }
        }
    ],
    "meta": {
        "keywords": "New Firm, 1965, Los Angeles, California, United States, Kyoto, Kyoto Prefecture, Japan, company, profile, biography, trivia, dbljump, video games, pc games, gaming",
        "description": "Find New Firm's game credits, profile, images and facts at Dbljump, the video game reference.",
        "created_at": "2017-06-27T22:28:07.651Z",
        "updated_at": "2017-06-27T22:28:07.651Z"
    }
}
```

Create a new company article. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/companies`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | 1-250 characters.
description | text | | 1-800 characters.
origin_date | date | | Between 1st Jan 1800 and the present.
origin_year | integer | | Between 1800 and the present year.
end | boolean | | True if the company has end.
end_date | date | | Between 1st Jan 1800 and the present.
end_year | integer | | Between 1800 and the present year.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
origin_place | belongs_to | | places | Can be a country, subdivision, or locality.
latest_place | belongs_to | | places | Can be a country, subdivision, or locality.
primary_image | belongs_to | | images | The main article image, usually the company logo.

### Success HTTP response code

`201 Created`
