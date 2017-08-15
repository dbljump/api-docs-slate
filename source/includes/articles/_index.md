## Get all articles

> Response body | `HTTP 200`

```JSON
# GET /articles?articles?page[size]=2&sort=-status&filter[type]=game

{
    "data": [
        {
            "id": "95",
            "type": "games",
            "attributes": {
                "display_title": "Shadow of the Beast",
                "sort_title": "Shadow of the Beast",
                "slug": "shadow-of-the-beast",
                "description": "Shadow of the Beast is 1989 fantasy platform game developed by Reflections and published by Psygnosis.",
                "last_submitted_at": null,
                "last_reviewed_at": null,
                "last_review_outcome": null,
                "last_review_comments": null,
                "published_at": "2017-08-15T09:33:50.976Z",
                "status": "published"
            },
            "relationships": {
                "primary_image": {
                    "data": {
                        "id": "87",
                        "type": "images"
                    },
                    "links": {
                        "related": "http://localhost:3000/media/images/shadow-of-the-beast-amiga-screenshot"
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
                }
            },
            "meta": {
                "description": "Find Shadow of the Beast trivia, screenshots, credits and other info at Dbljump, the video game reference.",
                "keywords": "Shadow of the Beast, 1989, Amiga, Atari ST, Commodore 64, Amstrad CPC, ZX Spectrum, Genesis, Master System, Lynx, FM Towns, TurboGrafx-CD, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-15T09:33:50.982Z",
                "updated_at": "2017-08-15T09:34:27.992Z"
            }
        },
        {
            "id": "94",
            "type": "games",
            "attributes": {
                "display_title": "North & South",
                "sort_title": "North & South",
                "slug": "north-south",
                "description": "North & South is a 1989 American Civil War-themed strategy game developed by Infogrames.",
                "last_submitted_at": null,
                "last_reviewed_at": null,
                "last_review_outcome": null,
                "last_review_comments": null,
                "published_at": "2017-08-15T09:33:50.928Z",
                "status": "published"
            },
            "relationships": {
                "primary_image": {
                    "data": {
                        "id": "86",
                        "type": "images"
                    },
                    "links": {
                        "related": "http://localhost:3000/media/images/north-south-atari-st-screenshot"
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
                }
            },
            "meta": {
                "description": "Find North & South trivia, screenshots, credits and other info at Dbljump, the video game reference.",
                "keywords": "North & South, 1989, Amiga, Atari ST, Commodore 64, MS-DOS, MSX, Nintendo Entertainment System, ZX Spectrum, Amstrad CPC, Nord et Sud, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-15T09:33:50.934Z",
                "updated_at": "2017-08-15T09:34:27.462Z"
            }
        }
    ],
    "included": [
        {
            "id": "87",
            "type": "images",
            "attributes": {
                "original": "http://localhost:3000/uploads/images/87/shadow-of-the-beast-amiga-screenshot-1708151034.jpg",
                "thumb": "http://localhost:3000/uploads/images/87/th_shadow-of-the-beast-amiga-screenshot-1708151034.jpg",
                "title": "Shadow of the Beast Amiga screenshot"
            },
            "links": {
                "self": "http://localhost:3000/media/images/shadow-of-the-beast-amiga-screenshot"
            },
            "meta": {
                "description": "'Shadow of the Beast Amiga screenshot' is a video game image at Dbljump.",
                "keywords": "Shadow of the Beast Amiga screenshot, screen, Psygnosis Limited, image, picture, media, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-15T09:34:27.853Z",
                "updated_at": "2017-08-15T09:34:27.853Z"
            }
        },
        {
            "id": "1",
            "type": "users",
            "attributes": {
                "username": "tikithekiwi",
                "avatar_thumb": "http://localhost:3000/uploads/user_avatar/1/th_tikithekiwi-1708151031.jpg"
            },
            "links": {
                "self": "http://localhost:3000/users/1"
            },
            "meta": {
                "description": "Tiki the Kiwi is a member at Dbljump, the video game reference.",
                "keywords": "tikithekiwi, Tiki the Kiwi, user, dbljump, video games, pc games, gaming",
                "last_signed_in_at": null,
                "last_sign_in_ip": null,
                "sign_in_count": 0,
                "activated_at": "2017-08-15T09:31:43.431Z",
                "created_at": "2017-08-15T09:31:45.327Z",
                "updated_at": "2017-08-15T09:31:45.327Z"
            }
        },
        {
            "id": "86",
            "type": "images",
            "attributes": {
                "original": "http://localhost:3000/uploads/images/86/north-south-atari-st-screenshot-1708151034.gif",
                "thumb": "http://localhost:3000/uploads/images/86/th_north-south-atari-st-screenshot-1708151034.gif",
                "title": "North & South Atari ST screenshot"
            },
            "links": {
                "self": "http://localhost:3000/media/images/north-south-atari-st-screenshot"
            },
            "meta": {
                "description": "'North & South Atari ST screenshot' is a video game image at Dbljump.",
                "keywords": "North & South Atari ST screenshot, screen, Infogrames, image, picture, media, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-15T09:34:27.293Z",
                "updated_at": "2017-08-15T09:34:27.293Z"
            }
        }
    ],
    "links": {
        "self": "http://localhost:3000/articles?filter%5Btype%5D=game&page%5Bnumber%5D=1&page%5Bsize%5D=2&sort=-id",
        "next": "http://localhost:3000/articles?filter%5Btype%5D=game&page%5Bnumber%5D=2&page%5Bsize%5D=2&sort=-id",
        "last": "http://localhost:3000/articles?filter%5Btype%5D=game&page%5Bnumber%5D=10&page%5Bsize%5D=2&sort=-id"
    },
    "meta": {
        "total_items": 19
    }
}
```

Retrieve a collection of articles.

### HTTP request

`GET /articles`

### URL queries

* See the ['Using URL queries' section](#using-url-queries) for more information and a table of sort query fields.

Filter field | Acceptable values
------------ | -----------------
type | `game`, `company`, `person`
status | `draft`, `submitted`, `published_at`
origin_date | `1800-01-01` or later
origin_year | `1800` or later
ended | `true` or `false`
end_date | `1800-01-01` or later
end_year | `1800` or later
created_by_id | Valid user ID
last_review_outcome | `ok`, `fail_style`, `fail_incomplete`, `fail_accuracy`

### Success HTTP response code

`200 OK`
