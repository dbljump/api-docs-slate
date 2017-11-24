## <a name="game_titles_create"></a>Create a new game title

> Request body | `POST /articles/game_titles`

```JSON
{
  "data": {
    "type": "game_titles",
    "attributes": {
      "title": "New Title",
      "kind": "title",
      "writing_system": "Latin"
    },
    "relationships": {
      "game": {
        "data": {
          "id": "47",
          "type": "games"
        }
      },
      "place": {
        "data": {
          "id": "17",
          "type": "places"
        }
      },
      "version": {
        "data": {
          "id": "2",
          "type": "game_versions"
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
    "id": "62",
    "type": "game_titles",
    "attributes": {
      "title": "New Title",
      "kind": "title",
      "writing_system": "Latin"
    },
    "relationships": {
      "game": {
        "data": {
          "id": "47",
          "type": "games"
        },
        "links": {
          "related": "http://localhost:3000/articles/games/dark-souls"
        }
      },
      "place": {
        "data": {
          "id": "17",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/bangladesh"
        }
      },
      "version": {
        "data": {
          "id": "2",
          "type": "versions"
        },
        "links": {
          "related": "http://localhost:3000/articles/game_versions/2"
        }
      }
    }
  },
  "included": [
    {
      "id": "47",
      "type": "games",
      "attributes": {
        "display_title": "Dark Souls"
      },
      "links": {
        "self": "http://localhost:3000/articles/games/dark-souls"
      }
    },
    {
      "id": "17",
      "type": "places",
      "attributes": {
        "name": "Bangladesh"
      },
      "links": {
        "self": "http://localhost:3000/places/bangladesh"
      }
    }
  ],
  "meta": {
    "keywords": "new title, dark souls, bangladesh, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "New Title is an alternate name or title for Dark Souls. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-05-13T12:43:38.980Z",
    "updated_at": "2017-05-13T12:43:38.980Z"
  }
}
```

Create a new game title record. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/game_titles`

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
game  | belongs_to  | Y  | games  | The game the title belongs to.
place | belongs_to | | places | Can be a country or region.
version | belongs_to | | game_versions | Version must belong to same game as title.

### Success HTTP response code

`201 Created`
