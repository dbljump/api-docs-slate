## <a name="game_titles_update"></a>Update a game title

> Request body | `PATCH /articles/game_titles/58`

```JSON
{
  "data": {
    "type": "game_titles",
    "id": "58",
    "attributes": {
      "title": "アップデート",
      "kind": "title",
      "writing_system": "Japanese"
    },
    "relationships": {
      "place": {
        "data": {
          "id": "102",
          "type": "places"
        }
      },
      "version": {
        "data": {
          "id": "1",
          "type": "game_versions"
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
    "id": "58",
    "type": "game_titles",
    "attributes": {
      "title": "アップデート",
      "kind": "title",
      "writing_system": "Japanese"
    },
    "relationships": {
      "game": {
        "data": {
          "id": "46",
          "type": "games"
        },
        "links": {
          "related": "http://localhost:3000/articles/games/the-wonderful-101"
        }
      },
      "place": {
        "data": {
          "id": "102",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/japan"
        }
      },
      "version": {
        "data": {
          "id": "1",
          "type": "versions"
        },
        "links": {
          "related": "http://localhost:3000/articles/game_versions/1"
        }
      }
    }
  },
  "included": [
    {
      "id": "46",
      "type": "games",
      "attributes": {
        "display_title": "The Wonderful 101"
      },
      "links": {
        "self": "http://localhost:3000/articles/games/the-wonderful-101"
      }
    },
    {
      "id": "102",
      "type": "places",
      "attributes": {
        "name": "Japan"
      },
      "links": {
        "self": "http://localhost:3000/places/japan"
      }
    }
  ],
  "meta": {
    "keywords": "アップデート, the wonderful 101, japan, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "アップデート is an alternate name or title for The Wonderful 101. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:19.450Z",
    "updated_at": "2017-05-13T12:58:30.190Z"
  }
}
```

Update an existing game title. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/game_titles/{id}` (replace `{id}` with record ID)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
title | string | Y | 1-250 characters.
kind | string | Y | The name classification. Must be 'title', 'working' or 'translated'.
writing_system | string | Y | Must be an accepted value.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
place | belongs_to | | places | Can be a country or region.
version | belongs_to | | game_versions | Version must belong to same game as title.

### Success HTTP response code

`200 OK`
