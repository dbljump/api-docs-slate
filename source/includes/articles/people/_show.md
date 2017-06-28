## <a name="people_show"></a>Get a single person

> Response body | `HTTP 200`

```JSON
# GET /articles/people/hideki-kamiya

{
    "data": {
        "id": "44",
        "type": "people",
        "attributes": {
            "display_title": "Hideki Kamiya",
            "description": "Hideki Kamiya is a game designer and director known for his work with Capcom and as a co-founder of PlatinumGames.",
            "slug": "hideki-kamiya",
            "last_submitted_at": null,
            "last_reviewed_at": null,
            "last_review_outcome": null,
            "last_review_comments": null,
            "published_at": "2017-06-28T17:04:26.704Z",
            "status": "published",
            "gender": "male",
            "birth_date": "1970-12-19",
            "birth_year": 1970,
            "dead": null,
            "death_date": null,
            "death_year": null
        },
        "relationships": {
            "primary_image": {
                "data": null,
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
                    "id": "2936",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/matsumoto-nagano-prefecture-japan"
                }
            },
            "death_place": {
                "data": null,
                "links": {
                    "related": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
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
                    "related": "http://localhost:3000/articles/people/hideki-kamiya/names"
                }
            },
            "notes": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/people/hideki-kamiya/notes"
                }
            },
            "images": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/people/hideki-kamiya/images"
                }
            },
            "credits": {
                "data": [],
                "links": {
                    "related": "http://localhost:3000/articles/people/hideki-kamiya/credits"
                }
            }
        },
        "links": {
            "self": "http://localhost:3000/articles/people/hideki-kamiya"
        }
    },
    "included": [
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
            "id": "2936",
            "type": "places",
            "attributes": {
                "name": "Matsumoto",
                "formatted": "Matsumoto, Nagano Prefecture, Japan"
            },
            "links": {
                "self": "http://localhost:3000/places/matsumoto-nagano-prefecture-japan"
            }
        }
    ],
    "meta": {
        "keywords": "Hideki Kamiya, 1970, Matsumoto, Nagano Prefecture, Japan, person, profile, biography, games, dbljump, video games, pc games, gaming",
        "description": "Find Hideki Kamiya's game credits, biography, images and facts at Dbljump, the video game reference.",
        "created_at": "2017-06-28T17:04:26.729Z",
        "updated_at": "2017-06-28T17:04:26.729Z"
    }
}
```

Retrieve a single person article. People are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/people/{slug}` (replace `{slug}` with record slug)

### Success HTTP response code

`200 OK`

### <a name="person_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | The article title, usually the person's name.
description | text | | A short biography up to 800 chars.
gender | string | | Must be 'male', 'female', 'transman' or 'transwoman'.
birth_date | date | | Between 1st Jan 1800 and the present.
birth_year | integer | | Between 1800 and the present year.
dead | boolean | | True if the person is dead.
death_date | date | | Between 1st Jan 1800 and the present.
death_year | integer | | Between 1800 and the present year.
slug | string | Y | A record ID based on the display_title.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
birth_place | places | belongs_to
death_place | places | belongs_to
created_by | users | belongs_to
primary_image | images | belongs_to

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar
places | birth_place | name, formatted
places | death_place | name, formatted
images | primary_image | title, file

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
