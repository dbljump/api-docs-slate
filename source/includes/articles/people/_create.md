## <a name="people_create"></a>Create a new person

> Request body | `POST /articles/people`

```JSON
{
  "data": {
    "type": "people",
    "attributes": {
      "given_names": "New",
      "family_name": "Person",
      "description": "New Person is a new person, and this describes them.",
      "gender": "female",
      "origin_date": "1965-09-12",
      "origin_year": "",
      "ended": "",
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
        "id": "140",
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
            "origin_date": "1965-09-12",
            "origin_year": 1965,
            "ended": true,
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
                    "related": "http://localhost:3000/media/images/nintendo-office"
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
                    "related": "http://localhost:3000/places/all-guernsey"
                }
            },
            "latest_place": {
                "data": {
                    "id": "2932",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/glasgow-scotland-united-kingdom"
                }
            },
            "names": {
                "data": [
                    {
                        "id": "191",
                        "type": "person_names"
                    }
                ],
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
        },
        "meta": {
            "description": "Find New Person's game credits, biography, images and facts at Dbljump, the video game reference.",
            "keywords": "New Person, 1965, All, Guernsey, New Person, person, profile, biography, games, dbljump, video games, pc games, gaming",
            "created_at": "2017-08-03T09:18:15.694Z",
            "updated_at": "2017-08-03T09:18:15.788Z"
        }
    },
    "included": [
        {
            "id": "1",
            "type": "images",
            "attributes": {
                "title": "Nintendo office"
            },
            "links": {
                "self": "http://localhost:3000/media/images/nintendo-office"
            },
            "meta": {
                "description": "'Nintendo office' is a video game image at Dbljump.",
                "keywords": "Nintendo office, photo, 2006, 2006-02-18, Moja~commonswiki, image, picture, media, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-03T09:13:25.111Z",
                "updated_at": "2017-08-03T09:13:25.111Z"
            }
        },
        {
            "id": "2",
            "type": "users",
            "attributes": {
                "username": "neil",
                "avatar": "http://localhost:3000/uploads/user_avatar/2/neil-1708031013.jpg"
            },
            "links": {
                "self": "http://localhost:3000/users/2"
            },
            "meta": {
                "description": "Neil Wheatley is a member at Dbljump, the video game reference.",
                "keywords": "neil, Neil Wheatley, user, dbljump, video games, pc games, gaming",
                "last_signed_in_at": null,
                "last_sign_in_ip": null,
                "sign_in_count": 0,
                "activated_at": "2017-08-03T09:13:20.434Z",
                "created_at": "2017-08-03T09:13:20.947Z",
                "updated_at": "2017-08-03T09:13:20.947Z"
            }
        },
        {
            "id": "2883",
            "type": "places",
            "attributes": {
                "name": "All",
                "formatted": "All, Guernsey"
            },
            "links": {
                "self": "http://localhost:3000/places/all-guernsey"
            },
            "meta": {
                "description": "Find video game companies and games industry professionals from All, Guernsey at Dbljump.",
                "keywords": "All, Guernsey, state, county, place, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-03T09:13:18.139Z",
                "updated_at": "2017-08-03T09:13:18.139Z"
            }
        },
        {
            "id": "2932",
            "type": "places",
            "attributes": {
                "name": "Glasgow",
                "formatted": "Glasgow, Scotland, United Kingdom"
            },
            "links": {
                "self": "http://localhost:3000/places/glasgow-scotland-united-kingdom"
            },
            "meta": {
                "description": "Find video game companies and games industry professionals from Glasgow, Scotland, United Kingdom at Dbljump.",
                "keywords": "Glasgow, Scotland, United Kingdom, city, town, place, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-03T09:13:19.411Z",
                "updated_at": "2017-08-03T09:13:19.411Z"
            }
        }
    ]
}
```

Create a new person article. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/people`

### Request attributes

Note that the `given_names` and `family_name` attributes are only used for creating records. Their values are used to set `display_title` and `sort_title`.

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
given_names | string | Y | Max 50 characters. Only used when creating a record.
family_name | string | | Max 50 characters. Only used when creating a record.
description | text | | 1-800 characters.
gender | string | | Must be 'male', 'female', 'transman' or 'transwoman'.
origin_date | date | | Between 1st Jan 1800 and the present.
origin_year | integer | | Between 1800 and the present year.
ended | boolean | | True if the person is dead.
end_date | date | | Between 1st Jan 1800 and the present.
end_year | integer | | Between 1800 and the present year.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
primary_image | belongs_to | | images | The main article image, usually a game poster.
origin_place | belongs_to | | places | Can be a country, subdivision, or locality.
latest_place | belongs_to | | places | Can be a country, subdivision, or locality.

### Success HTTP response code

`201 Created`
