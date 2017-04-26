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
      "gender": "female",
      "birth_date": "1965-09-12",
      "birth_year": 1965,
      "dead": true,
      "death_date": "2012-05-18",
      "death_year": 2012,
      "slug": "new-person"
    },
    "relationships": {
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
      "created_by": {
        "data": {
          "id": "2",
          "type": "users"
        },
        "links": {
          "related": "http://localhost:3000/users/2"
        }
      }
    },
    "links": {
      "self": "http://localhost:3000/articles/people/new-person"
    }
  },
  "included": [
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
    },
    {
      "id": "2",
      "type": "users",
      "attributes": {
        "username": "neil",
        "role": "admin",
        "given_names": "Neil",
        "family_name": "Wheatley",
        "avatar": "http://localhost:3000/uploads/user_avatar/2/1704241009.jpg"
      },
      "links": {
        "self": "http://localhost:3000/users/2"
      }
    }
  ],
  "meta": {
    "keywords": "new person, 1965, 1965-09-12, los angeles, california, united states, person, profile, biography, games, dbljump, video games, pc games, gaming",
    "description": "Find New Person's game credits, biography, images and facts at Dbljump, the video game reference.",
    "created_at": "2017-04-26T16:42:37.944Z",
    "updated_at": "2017-04-26T16:42:37.944Z"
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
birth_place | belongs_to | | places | Can be a country, subdivision, or locality.
death_place | belongs_to | | places | Can be a country, subdivision, or locality.

### Success HTTP response code

`201 Created`
