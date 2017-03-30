## <a name="localities_create"></a>Create a new locality record

> Request body

```JSON
{
  "data": {
    "type": "places",
    "attributes": {
      "subdivision_id": "1000",
      "name": "New City",
      "also_known_as": ["That New City", "The New Locality"],
      "latitude": "81.3",
      "longitude": "-45.9"
    }
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "2939",
    "type": "places",
    "attributes": {
      "subtype": "localities",
      "slug": "new-city-enugu-nigeria",
      "name": "New City",
      "short_name": null,
      "formatted": "New City, Enugu, Nigeria",
      "also_known_as": [
        "That New City",
        "The New Locality"
      ],
      "latitude": 81.3,
      "longitude": -45.9
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
      "country": {
        "data": {
          "id": "150",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/countries/nigeria"
        }
      },
      "subdivision": {
        "data": {
          "id": "1000",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/subdivisions/enugu-nigeria"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/places/localities/new-city-enugu-nigeria"
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
        "avatar": {
          "url": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1703301240.jpg"
        }
      },
      "links": {
        "self": "http://api.dbljump.com/users/2"
      }
    },
    {
      "id": "150",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "nigeria",
        "name": "Nigeria",
        "short_name": null,
        "formatted": "Nigeria"
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/nigeria"
      }
    },
    {
      "id": "1000",
      "type": "places",
      "attributes": {
        "subtype": "subdivisions",
        "slug": "enugu-nigeria",
        "name": "Enugu",
        "short_name": null,
        "formatted": "Enugu, Nigeria"
      },
      "links": {
        "self": "http://api.dbljump.com/places/subdivisions/enugu-nigeria"
      }
    }
  ],
  "meta": {
    "keywords": "new city, enugu, nigeria, that new city, the new locality, city, town, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from New City, Enugu, Nigeria at Dbljump.",
    "created_at": "2017-03-30T13:50:25.595Z",
    "updated_at": "2017-03-30T13:50:25.595Z"
  }
}
```

Create a new locality record. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /places/localities`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
subdivision_id | integer | Y | ID of parent subdivision.
name | string | Y | 2-250 chars. English-language common name, e.g. 'Los Angeles'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['LA', 'City of Angels']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Success HTTP response code

`201 Created`
