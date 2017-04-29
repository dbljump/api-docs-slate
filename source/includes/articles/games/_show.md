## <a name="games_show"></a>Get a single game

> Response body | `HTTP 200`

```JSON
# GET /articles/games/the-wonderful-101

{
  "data": {
    "id": "46",
    "type": "games",
    "attributes": {
      "display_title": "The Wonderful 101",
      "description": "The Wonderful 101 is an action-adventure video game developed by Platinum Games for the Nintendo Wii U.",
      "release_date": "2013-08-23",
      "release_year": 2013,
      "slug": "the-wonderful-101"
    },
    "relationships": {
      "created_by": {
        "data": {
          "id": "1",
          "type": "users"
        },
        "links": {
          "related": "http://localhost:3000/users/1"
        }
      }
    },
    "links": {
      "self": "http://localhost:3000/articles/games/the-wonderful-101"
    }
  },
  "included": [
    {
      "id": "1",
      "type": "users",
      "attributes": {
        "username": "tikithekiwi",
        "role": "admin",
        "given_names": "Tiki",
        "family_name": "the Kiwi",
        "avatar": null
      },
      "links": {
        "self": "http://localhost:3000/users/1"
      }
    }
  ],
  "meta": {
    "keywords": "the wonderful 101, 2013, game, credits, screenshots, trivia, dbljump, video games, pc games, gaming",
    "description": "Find The Wonderful 101 trivia, screenshots, credits and other info at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:19.130Z",
    "updated_at": "2017-04-24T09:09:19.130Z"
  }
}
```

Retrieve a single game article. Games are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{slug}` (replace `{slug}` with record slug)

### Success HTTP response code

`200 OK`

### <a name="person_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | The article title, usually the company name.
description | text | | A short biography up to 800 chars.
release_date | date | | Between 1st Jan 1800 and the present.
release_year | integer | | Between 1800 and the present year.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
created_by | users | belongs_to

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
