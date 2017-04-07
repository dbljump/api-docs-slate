## Region countries: get all

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "12",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "australia",
        "name": "Australia",
        "short_name": null,
        "formatted": "Australia",
        "iso_code": "AU",
        "also_known_as": [],
        "nationality": "Australian",
        "currency": null,
        "longitude": 133,
        "latitude": -27
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
        "regions": {
          "data": [
            {
              "id": "239",
              "type": "places"
            }
          ],
          "links": {
            "related": "http://api.dbljump.com/places/countries/australia/regions"
          }
        },
        "subdivisions": {
          "links": {
            "related": "http://api.dbljump.com/places/countries/australia/subdivisions"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/australia"
      }
    },
    {
      "id": "147",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "new-zealand",
        "name": "New Zealand",
        "short_name": null,
        "formatted": "New Zealand",
        "iso_code": "NZ",
        "also_known_as": [],
        "nationality": "New Zealander",
        "currency": null,
        "longitude": 174,
        "latitude": -41
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
        "regions": {
          "data": [
            {
              "id": "239",
              "type": "places"
            }
          ],
          "links": {
            "related": "http://api.dbljump.com/places/countries/new-zealand/regions"
          }
        },
        "subdivisions": {
          "links": {
            "related": "http://api.dbljump.com/places/countries/new-zealand/subdivisions"
          }
        }
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/new-zealand"
      }
    }
  ],
  "links": {},
  "meta": {
    "total_items": 2
  }
}
```

Retrieve all countries belonging to the given region. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/regions/{region-slug}/countries` (replace `{region-slug}` with region record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
