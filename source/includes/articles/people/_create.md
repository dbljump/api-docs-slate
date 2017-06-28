## <a name="people_create"></a>Create a new person

> Request body | `POST /articles/people`

```JSON
{
  "data": {
    "type": "people",
    "attributes": {
      "display_title": "New Person",
      "description": "New Person is a new person, and this describes them.",
      "gender": "female",
      "birth_date": "1965-09-12",
      "birth_year": "",
      "dead": "",
      "death_date": "2012-05-18",
      "death_year": ""
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
          "id": "2883",
          "type": "places"
        }
      },
      "death_place": {
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
        "id": "48",
        "type": "people",
        "attributes": {
            "display_title": "New Person",
            "description": "New Person is a new person, and this describes them.",
            "slug": "new-person",
            "last_submitted_at": null,
            "last_reviewed_at": null,
            "last_review_outcome": null,
            "last_review_comments": null,
            "published_at": null,
            "status": "draft",
            "gender": "female",
            "birth_date": "1965-09-12",
            "birth_year": 1965,
            "dead": true,
            "death_date": "2012-05-18",
            "death_year": 2012
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
            "birth_place": {
                "data": {
                    "id": "2883",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/los-angeles-california-united-states"
                }
            },
            "death_place": {
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
                    "related": "http://localhost:3000/articles/people/new-person/names"
                }
            },
            "notes": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/people/new-person/notes"
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
                    "related": "http://localhost:3000/articles/people/new-person/images"
                }
            },
            "credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/people/new-person/credits"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/articles/people/new-person"
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
                "avatar": "http://localhost:3000/uploads/user_avatar/2/1706281804.jpg"
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
        "keywords": "New Person, 1965, Los Angeles, California, United States, person, profile, biography, games, dbljump, video games, pc games, gaming",
        "description": "Find New Person's game credits, biography, images and facts at Dbljump, the video game reference.",
        "created_at": "2017-06-28T17:10:26.129Z",
        "updated_at": "2017-06-28T17:10:26.129Z"
    }
}
```

Create a new person article. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/people`

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
primary_image | belongs_to | | images | The main article image, usually a game poster.
birth_place | belongs_to | | places | Can be a country, subdivision, or locality.
death_place | belongs_to | | places | Can be a country, subdivision, or locality.

### Success HTTP response code

`201 Created`
