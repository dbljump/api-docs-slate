## <a name="regions_update"></a>Update a region record

> Request body

```JSON
{
  "data": {
    "type": "places",
    "id": "europe",
    "attributes": {
      "name": "Updated Region",
      "short_name": "UR",
      "also_known_as": ["Edited Region", "Changed Region"],
      "latitude": "7.7",
      "longitude": "-65.4"
    },
    "relationships": {
  		"countries": {
  			"data": [
          { "type": "places", "id": "5" },
          { "type": "places", "id": "50" }
        ]
  		}
  	}
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "234",
    "type": "places",
    "attributes": {
      "subtype": "regions",
      "slug": "updated-region",
      "name": "Updated Region",
      "short_name": "UR",
      "formatted": "Updated Region",
      "latitude": 7.7,
      "longitude": -65.4,
      "also_known_as": [
        "Edited Region",
        "Changed Region"
      ]
    },
    "relationships": {
      "created_by": {
        "data": {
          "id": "1",
          "type": "users"
        },
        "links": {
          "related": "http://api.dbljump.com/users/1"
        }
      },
      "countries": {
        "data": [
          {
            "id": "5",
            "type": "places"
          },
          {
            "id": "50",
            "type": "places"
          }
        ],
        "links": {
          "related": "http://api.dbljump.com/places/regions/updated-region/countries"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/regions/updated-region"
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
        "self": "http://api.dbljump.com/users/1"
      }
    }
  ],
  "meta": {
    "keywords": "updated region, ur, edited region, changed region, place, geography, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Updated Region at Dbljump.",
    "created_at": "2017-04-05T13:55:46.264Z",
    "updated_at": "2017-04-07T10:56:46.781Z"
  }
}
```

Update an existing region record. The user must be an admin.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /places/regions/{slug}` (replace `{slug}` with region record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | Unique. 2-50 chars. English-language common name, e.g. 'North America'.
short_name | string | | Unique. 2-20 chars. Common short name, e.g. 'NA'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['Norteamérica']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | ----------
countries | has_many |  | places (countries) | The [countries](#countries_intro) that belong to this region.

### Success HTTP response code

`200 OK`
