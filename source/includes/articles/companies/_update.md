## <a name="companies_update"></a>Update a company

> Request body | `PATCH /articles/companies/microsoft-corporation`

```JSON
{
  "data": {
    "type": "companies",
    "id": "microsoft-corporation",
    "attributes": {
      "display_title": "Changed Name",
      "description": "Updated description for an updated article.",
      "origin_date": "1940-09-12",
      "origin_year": "",
      "dead": "",
      "end_date": "2013-04-05",
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
          "id": "25",
          "type": "places"
        }
      },
      "latest_place": {
        "data": {
          "id": "2933",
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
        "id": "4",
        "type": "companies",
        "attributes": {
            "display_title": "Changed Name",
            "description": "Updated description for an updated article.",
            "slug": "changed-name",
            "last_submitted_at": null,
            "last_reviewed_at": null,
            "last_review_outcome": null,
            "last_review_comments": null,
            "published_at": "2017-06-28T17:04:18.271Z",
            "status": "published",
            "origin_date": "1940-09-12",
            "origin_year": 1940,
            "end": true,
            "end_date": "2013-04-05",
            "end_year": 2013
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
            "origin_place": {
                "data": {
                    "id": "25",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/bolivia"
                }
            },
            "latest_place": {
                "data": {
                    "id": "2933",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/sonobe-kyoto-prefecture-japan"
                }
            },
            "names": {
                "data": [
                    {
                        "id": "12",
                        "type": "company_names"
                    },
                    {
                        "id": "13",
                        "type": "company_names"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/changed-name/names"
                }
            },
            "notes": {
                "data": [
                    {
                        "id": "5",
                        "type": "company_notes"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/changed-name/notes"
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
                    "related": "http://localhost:3000/articles/companies/changed-name/images"
                }
            },
            "credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/companies/changed-name/credits"
                }
            },
            "parents": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/companies/changed-name/parents"
                }
            },
            "children": {
                "data": [
                    {
                        "id": "17",
                        "type": "company_kinships"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/companies/changed-name/children"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/articles/companies/changed-name"
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
            "id": "25",
            "type": "places",
            "attributes": {
                "name": "Bolivia",
                "formatted": "Bolivia"
            },
            "links": {
                "self": "http://localhost:3000/places/bolivia"
            }
        },
        {
            "id": "2933",
            "type": "places",
            "attributes": {
                "name": "Sonobe",
                "formatted": "Sonobe, Kyoto Prefecture, Japan"
            },
            "links": {
                "self": "http://localhost:3000/places/sonobe-kyoto-prefecture-japan"
            }
        }
    ],
    "meta": {
        "keywords": "Changed Name, 1940, Bolivia, Sonobe, Kyoto Prefecture, Japan, MS, Microsoft, company, profile, biography, trivia, dbljump, video games, pc games, gaming",
        "description": "Find Changed Name's game credits, profile, images and facts at Dbljump, the video game reference.",
        "created_at": "2017-06-28T17:04:18.295Z",
        "updated_at": "2017-06-28T17:05:53.641Z"
    }
}
```

Update an existing company article. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/companies/{slug}` (replace `{slug}` with record slug)

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
primary_image | belongs_to | | images | The main article image, usually a company logo.
birth_place | belongs_to | | places | Can be a country, subdivision, or locality.
death_place | belongs_to | | places | Can be a country, subdivision, or locality.

### Success HTTP response code

`200 OK`
