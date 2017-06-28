## <a name="people_update"></a>Update a person

> Request body | `PATCH /articles/people/hideki-kamiya`

```JSON
{
  "data": {
    "type": "people",
    "id": "hideki-kamiya",
    "attributes": {
      "display_title": "Changed Name",
      "description": "Updated description for an updated article.",
      "gender": "transwoman",
      "birth_date": "1960-09-12",
      "birth_year": "",
      "dead": "",
      "death_date": "",
      "death_year": "2015"
    },
    "relationships": {
      "primary_image": {
        "data": {
          "id": "1",
          "type": "images"
        }
      },
      "birth_place": {
        "data": {
          "id": "25",
          "type": "places"
        }
      },
      "death_place": {
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
        "id": "44",
        "type": "people",
        "attributes": {
            "display_title": "Changed Name",
            "description": "Updated description for an updated article.",
            "slug": "changed-name-c7bbffd2-15e1-4008-98b3-96268e466d0f",
            "last_submitted_at": null,
            "last_reviewed_at": null,
            "last_review_outcome": null,
            "last_review_comments": null,
            "published_at": "2017-06-28T17:04:26.704Z",
            "status": "published",
            "gender": "transwoman",
            "birth_date": "1960-09-12",
            "birth_year": 1960,
            "dead": true,
            "death_date": null,
            "death_year": 2015
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
            "birth_place": {
                "data": {
                    "id": "25",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/bolivia"
                }
            },
            "death_place": {
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
                        "id": "57",
                        "type": "person_names"
                    }
                ],
                "links": {
                    "related": "http://localhost:3000/articles/people/changed-name-c7bbffd2-15e1-4008-98b3-96268e466d0f/names"
                }
            },
            "notes": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/people/changed-name-c7bbffd2-15e1-4008-98b3-96268e466d0f/notes"
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
                    "related": "http://localhost:3000/articles/people/changed-name-c7bbffd2-15e1-4008-98b3-96268e466d0f/images"
                }
            },
            "credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/people/changed-name-c7bbffd2-15e1-4008-98b3-96268e466d0f/credits"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/articles/people/changed-name-c7bbffd2-15e1-4008-98b3-96268e466d0f"
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
        "keywords": "Changed Name, 1960, Bolivia, 神谷 英樹, person, profile, biography, games, dbljump, video games, pc games, gaming",
        "description": "Find Changed Name's game credits, biography, images and facts at Dbljump, the video game reference.",
        "created_at": "2017-06-28T17:04:26.729Z",
        "updated_at": "2017-06-28T17:13:03.539Z"
    }
}
```

Update an existing person article. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/people/{slug}` (replace `{slug}` with record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | 1-250 characters.
description | text | | 1-800 characters.
gender | string | | Must be 'male', 'female', 'transman' or 'transwoman'.
birth_date | date | | Between 1st Jan 1800 and the present.
birth_year | integer | | Between 1800 and the present year.
dead | boolean | | True if the person is dead.
death_date | date | | Between 1st Jan 1800 and the present.
death_year | integer | | Between 1800 and the present year.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
primary_image | belongs_to | | images | The main article image, usually a likeness of the person.
birth_place | belongs_to | | places | Can be a country, subdivision, or locality.
death_place | belongs_to | | places | Can be a country, subdivision, or locality.

### Success HTTP response code

`200 OK`
