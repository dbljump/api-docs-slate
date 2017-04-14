## <a name="places_regions_index"></a>Get all place regions

> Response body | `HTTP 200`

```JSON
# GET /places/united-states/regions

{
  "data": [
    {
      "id": "238",
      "type": "places",
      "attributes": {
        "kind": "region",
        "slug": "us-and-canada",
        "name": "US and Canada",
        "formatted": "US and Canada",
        "short_name": "US&Ca",
        "also_known_as": [],
        "latitude": null,
        "longitude": null,
        "iso_code": null
      },
      "relationships": {
        "parent": {
          "data": null
        },
        "children": {
          "data": [
            {
              "id": "36",
              "type": "places"
            },
            {
              "id": "220",
              "type": "places"
            }
          ],
          "links": {
            "related": "http://api.dbljump.com/places/us-and-canada/children"
          }
        },
        "regions": {
          "data": null,
          "links": {
            "related": "http://api.dbljump.com/places/us-and-canada/regions"
          }
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://api.dbljump.com/users/1"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/us-and-canada"
      }
    },
    {
      "id": "233",
      "type": "places",
      "attributes": {
        "kind": "region",
        "slug": "north-america",
        "name": "North America",
        "formatted": "North America",
        "short_name": "NA",
        "also_known_as": [],
        "latitude": null,
        "longitude": null,
        "iso_code": null
      },
      "relationships": {
        "parent": {
          "data": null
        },
        "children": {
          "data": [
            {
              "id": "36",
              "type": "places"
            },
            {
              "id": "133",
              "type": "places"
            },
            {
              "id": "220",
              "type": "places"
            }
          ],
          "links": {
            "related": "http://api.dbljump.com/places/north-america/children"
          }
        },
        "regions": {
          "data": null,
          "links": {
            "related": "http://api.dbljump.com/places/north-america/regions"
          }
        },
        "created_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://api.dbljump.com/users/1"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/north-america"
      }
    }
  ],
  "links": {},
  "meta": {
    "total_items": 2
  }
}
```

Retrieve all regions that a given country belongs to. Returns a `404` error for regions, subdivision, and localities. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/{place-slug}/regions`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[places] | All fields | Return only specified fields, e.g. `/places/japan/regions?fields[images]=name`
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
