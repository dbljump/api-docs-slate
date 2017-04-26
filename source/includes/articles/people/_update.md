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
      "gender": "transwoman",
      "birth_date": "1960-09-12",
      "birth_year": 1960,
      "dead": true,
      "death_date": null,
      "death_year": 2015,
      "slug": "changed-name"
    },
    "relationships": {
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
      "self": "http://localhost:3000/articles/people/changed-name"
    }
  },
  "included": [
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
    "keywords": "changed name, 1960, 1960-09-12, bolivia, person, profile, biography, games, dbljump, video games, pc games, gaming",
    "description": "Find Changed Name's game credits, biography, images and facts at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:17.259Z",
    "updated_at": "2017-04-26T21:38:21.753Z"
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
birth_place | belongs_to | | places | Can be a country, subdivision, or locality.
death_place | belongs_to | | places | Can be a country, subdivision, or locality.

### Success HTTP response code

`200 OK`
