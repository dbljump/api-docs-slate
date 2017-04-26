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
      "gender": "male",
      "birth_date": "1970-12-19",
      "birth_year": 1970,
      "dead": null,
      "death_date": null,
      "death_year": null,
      "slug": "hideki-kamiya"
    },
    "relationships": {
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
        "data": null
      },
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
      "self": "http://localhost:3000/articles/people/hideki-kamiya"
    }
  },
  "included": [
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
    },
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
    "keywords": "hideki kamiya, 1970, 1970-12-19, matsumoto, nagano prefecture, japan, person, profile, biography, games, dbljump, video games, pc games, gaming",
    "description": "Find Hideki Kamiya's game credits, biography, images and facts at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:17.259Z",
    "updated_at": "2017-04-24T09:09:17.259Z"
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


### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar
places | birth_place | name, formatted
places | death_place | name, formatted

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
