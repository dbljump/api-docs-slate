## Get all articles

> Response body | `HTTP 200`

```JSON
# GET /articles?articles?page[size]=3&sort=-status&filter[type]=Game

{
    "data": [
        {
            "id": "77",
            "type": "games",
            "attributes": {
                "display_title": "Pong",
                "sort_title": "Pong",
                "slug": "pong",
                "description": "Pong is a table tennis sports game and is one of the earliest arcade video games.",
                "last_submitted_at": null,
                "last_reviewed_at": null,
                "last_review_outcome": null,
                "last_review_comments": null,
                "published_at": "2017-08-08T12:27:05.229Z",
                "status": "published"
            },
            "relationships": {
                "primary_image": {
                    "data": null,
                    "links": {
                        "related": "http://localhost:3000/media/images/dark-souls-firelink-shrine-crow-screenshot"
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
                "description": "Find Pong trivia, screenshots, credits and other info at Dbljump, the video game reference.",
                "keywords": "Pong, 1972, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-08T12:27:05.299Z",
                "updated_at": "2017-08-08T12:27:05.299Z"
            }
        },
        {
            "id": "78",
            "type": "games",
            "attributes": {
                "display_title": "The Wonderful 101",
                "sort_title": "Wonderful 101, The",
                "slug": "the-wonderful-101",
                "description": "The Wonderful 101 is an action-adventure video game developed by Platinum Games for the Nintendo Wii U.",
                "last_submitted_at": null,
                "last_reviewed_at": null,
                "last_review_outcome": null,
                "last_review_comments": null,
                "published_at": "2017-08-08T12:27:05.322Z",
                "status": "published"
            },
            "relationships": {
                "primary_image": {
                    "data": {
                        "id": "70",
                        "type": "images"
                    },
                    "links": {
                        "related": "http://localhost:3000/media/images/pong-arcade-screenshot"
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
                "description": "Find The Wonderful 101 trivia, screenshots, credits and other info at Dbljump, the video game reference.",
                "keywords": "The Wonderful 101, 2013, Wii U, Switch, ザ・ワンダフル・ワン・オー・ワン, Za Wandafuru Wan Ō Wan, Project P-100, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-08T12:27:05.328Z",
                "updated_at": "2017-08-08T12:27:17.996Z"
            }
        },
        {
            "id": "79",
            "type": "games",
            "attributes": {
                "display_title": "Dark Souls",
                "sort_title": "Dark Souls",
                "slug": "dark-souls",
                "description": "Dark Souls is a dark-fantasy action role-playing game developed by FromSoftware.",
                "last_submitted_at": null,
                "last_reviewed_at": null,
                "last_review_outcome": null,
                "last_review_comments": null,
                "published_at": "2017-08-08T12:27:05.352Z",
                "status": "published"
            },
            "relationships": {
                "primary_image": {
                    "data": {
                        "id": "71",
                        "type": "images"
                    },
                    "links": {
                        "related": "http://localhost:3000/media/images/dark-souls-firelink-shrine-crow-screenshot"
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
                "description": "Find Dark Souls trivia, screenshots, credits and other info at Dbljump, the video game reference.",
                "keywords": "Dark Souls, 2011, PlayStation 3, Xbox 360, Windows, Dark Lord, Dark Race, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-08T12:27:05.364Z",
                "updated_at": "2017-08-08T12:27:19.037Z"
            }
        }
    ],
    "included": [
        {
            "id": "1",
            "type": "users",
            "attributes": {
                "username": "tikithekiwi",
                "avatar_thumb": "http://localhost:3000/uploads/user_avatar/1/th_tikithekiwi-1708081324.jpg"
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
                "activated_at": "2017-08-08T12:24:54.142Z",
                "created_at": "2017-08-08T12:24:54.955Z",
                "updated_at": "2017-08-08T12:24:54.955Z"
            }
        },
        {
            "id": "70",
            "type": "images",
            "attributes": {
                "original": "http://localhost:3000/uploads/images/70/pong-arcade-screenshot-1708081327.jpg",
                "thumb": "http://localhost:3000/uploads/images/70/th_pong-arcade-screenshot-1708081327.jpg",
                "title": "Pong arcade screenshot"
            },
            "links": {
                "self": "http://localhost:3000/media/images/pong-arcade-screenshot"
            },
            "meta": {
                "description": "'Pong arcade screenshot' is a video game image at Dbljump.",
                "keywords": "Pong arcade screenshot, screen, Nintendo Co., Ltd., image, picture, media, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-08T12:27:17.922Z",
                "updated_at": "2017-08-08T12:27:17.922Z"
            }
        },
        {
            "id": "71",
            "type": "images",
            "attributes": {
                "original": "http://localhost:3000/uploads/images/71/dark-souls-firelink-shrine-crow-screenshot-1708081327.jpg",
                "thumb": "http://localhost:3000/uploads/images/71/th_dark-souls-firelink-shrine-crow-screenshot-1708081327.jpg",
                "title": "Dark Souls Firelink Shrine crow screenshot"
            },
            "links": {
                "self": "http://localhost:3000/media/images/dark-souls-firelink-shrine-crow-screenshot"
            },
            "meta": {
                "description": "'Dark Souls Firelink Shrine crow screenshot' is a video game image at Dbljump.",
                "keywords": "Dark Souls Firelink Shrine crow screenshot, screen, Bandai Namco Entertainment, image, picture, media, dbljump, video games, pc games, gaming",
                "created_at": "2017-08-08T12:27:18.950Z",
                "updated_at": "2017-08-08T12:27:18.950Z"
            }
        }
    ],
    "links": {
        "self": "http://localhost:3000/articles?filter%5Btype%5D=Game&page%5Bnumber%5D=1&page%5Bsize%5D=3&sort=-status",
        "next": "http://localhost:3000/articles?filter%5Btype%5D=Game&page%5Bnumber%5D=2&page%5Bsize%5D=3&sort=-status",
        "last": "http://localhost:3000/articles?filter%5Btype%5D=Game&page%5Bnumber%5D=7&page%5Bsize%5D=3&sort=-status"
    },
    "meta": {
        "total_items": 19
    }
}
```

Retrieve a collection of articles.

### HTTP request

`GET /articles`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[images]=title,thumb`
filter[{field}] | All records | Filter search by field, e.g. `?filter[closed]=true`
sort | `sort_title` | Sort records by field, e.g. `?sort=status`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
