## <a name="version_releases_update"></a>Update a game version release

> Request body | `PATCH /articles/game_version_releases/1`

```JSON
{
  "data": {
    "type": "version_releases",
    "id": "1",
    "attributes": {
      "date": "2016-08-14",
      "year": "",
      "physical": "true",
      "digital": "false"
    },
    "relationships": {
      "place": {
        "data": {
          "id": "90",
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
        "id": "1",
        "type": "version_releases",
        "attributes": {
            "date": "2016-08-14",
            "year": 2016,
            "physical": true,
            "digital": false
        },
        "relationships": {
            "version": {
                "data": {
                    "id": "1",
                    "type": "game_versions"
                },
                "links": {
                    "related": "http://localhost:3000/articles/game_versions/1"
                }
            },
            "place": {
                "data": {
                    "id": "90",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/hong-kong"
                }
            }
        }
    },
    "included": [
        {
            "id": "90",
            "type": "places",
            "attributes": {
                "formatted": "Hong Kong"
            },
            "links": {
                "self": "http://localhost:3000/places/hong-kong"
            }
        }
    ],
    "meta": {
        "keywords": "The Wonderful 101, Wii U, Hong Kong, release, dbljump, video games, pc games, gaming",
        "description": "",
        "created_at": "2017-06-22T13:51:23.959Z",
        "updated_at": "2017-06-27T21:03:09.428Z"
    }
}
```

Update an existing game version release. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/game_version_releases/{id}` (replace `{id}` with record ID)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
date | date |  | Release date, e.g. '2013-08-24' for 24 August 2013.
year | number | | Release year. Auto-filled if date present.
physical | boolean | | True if release included physical format (e.g. disc or cartridge)
digital | boolean | | True if release included digital format (i.e. download)

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
place | belongs_to | Y | places | Release country or region. There can be one game version release per place.

### Success HTTP response code

`200 OK`
