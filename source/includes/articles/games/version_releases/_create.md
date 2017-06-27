## <a name="version_releases_create"></a>Create a new game version release

> Request body | `POST /articles/game_versions/1/releases`

```JSON
{
  "data": {
    "type": "version_releases",
    "attributes": {
      "date": "2013-08-01",
      "year": "",
      "physical": "false",
      "digital": "true"
    },
    "relationships": {
      "place": {
        "data": {
          "id": "102",
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
        "id": "13",
        "type": "version_releases",
        "attributes": {
            "date": "2013-08-01",
            "year": 2013,
            "physical": false,
            "digital": true
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
                    "id": "1",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/afghanistan"
                }
            }
        }
    },
    "included": [
        {
            "id": "1",
            "type": "places",
            "attributes": {
                "formatted": "Afghanistan"
            },
            "links": {
                "self": "http://localhost:3000/places/afghanistan"
            }
        }
    ],
    "meta": {
        "keywords": "The Wonderful 101, Wii U, Afghanistan, release, dbljump, video games, pc games, gaming",
        "description": "",
        "created_at": "2017-06-27T20:48:15.095Z",
        "updated_at": "2017-06-27T20:48:15.095Z"
    }
}
```

Create a new game version release. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/game_versions/{version-id}/releases` (replace `{version-id}` with game version ID)

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

`201 Created`
