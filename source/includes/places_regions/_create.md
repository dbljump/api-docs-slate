## <a name="regions_create"></a>Create a new region record

> Request body

```JSON
{
  "data": {
    "type": "places",
    "attributes": {
      "name": "New Region",
      "short_name": "NR",
      "also_known_as": ["That New Region", "The Newest"],
      "latitude": "5.0",
      "longitude": "-35.00"
    },
    "relationships": {
  		"countries": {
  			"data": [
          { "type": "places", "id": "7" },
          { "type": "places", "id": "27" }
        ]
  		}
  	}
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "2937",
    "type": "places",
    "attributes": {
      "subtype": "regions",
      "slug": "new-region",
      "name": "New Region",
      "short_name": "NR",
      "formatted": "New Region",
      "latitude": 5,
      "longitude": -35,
      "also_known_as": [
        "That New Region",
        "The Newest"
      ]
    },
    "relationships": {
      "created_by": {
        "data": {
          "id": "2",
          "type": "users"
        },
        "links": {
          "related": "http://api.dbljump.com/users/2"
        }
      },
      "countries": {
        "data": [
          {
            "id": "7",
            "type": "places"
          },
          {
            "id": "27",
            "type": "places"
          }
        ],
        "links": {
          "related": "http://api.dbljump.com/places/regions/new-region/countries"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/regions/new-region"
    }
  },
  "included": [
    {
      "id": "2",
      "type": "users",
      "attributes": {
        "username": "neil",
        "role": "admin",
        "given_names": "Neil",
        "family_name": "Wheatley",
        "avatar": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1704070637.jpeg"
      },
      "links": {
        "self": "http://api.dbljump.com/users/2"
      }
    }
  ],
  "meta": {
    "keywords": "new region, nr, that new region, the newest, place, geography, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from New Region at Dbljump.",
    "created_at": "2017-04-07T10:51:36.588Z",
    "updated_at": "2017-04-07T10:51:36.588Z"
  }
}
```

Create a new region record. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /places/regions`

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

`201 Created`
