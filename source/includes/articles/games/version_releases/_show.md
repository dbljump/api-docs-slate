## <a name="version_releases_show"></a>Get a single game version release

> Response body | `HTTP 200`

```JSON
# GET /articles/game_version_releases/1

{
    "data": {
        "id": "1",
        "type": "version_releases",
        "attributes": {
            "date": "2013-08-23",
            "year": 2013,
            "physical": true,
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
                    "id": "234",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/europe"
                }
            }
        }
    },
    "included": [
        {
            "id": "234",
            "type": "places",
            "attributes": {
                "formatted": "Europe"
            },
            "links": {
                "self": "http://localhost:3000/places/europe"
            }
        }
    ],
    "meta": {
        "keywords": "The Wonderful 101, Wii U, Europe, release, dbljump, video games, pc games, gaming",
        "description": "",
        "created_at": "2017-06-22T13:51:23.959Z",
        "updated_at": "2017-06-22T13:51:23.959Z"
    }
}
```

Retrieve a single game version release. Releases are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/game_version_releases/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`

### <a name="version_release_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
date | date | | Release date, e.g. '2013-08-24' for 24 August 2013.
year | number | | Release year. Auto-filled if date present.
physical | boolean | | True if release included physical format (e.g. disc or cartridge)
digital | boolean | | True if release included digital format (i.e. download)

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
place | places | belongs_to
version | game_versions | belongs_to

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
