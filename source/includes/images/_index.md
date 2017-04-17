## Get all images

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "1",
      "type": "images",
      "attributes": {
        "slug": "nintendo-office-2006-uncategorized-moja-commonswiki",
        "file": "url": "https://dbljumpheroku.s3.amazonaws.com/uploads/images/1/nintendo-hq-kyoto-2006.jpg",
        "kind": "photo",
        "title": "Nintendo office",
        "description": "Head Quarters of Nintendo, Minami-ku, Kyoto, Japan. The picture was taken by the poster in February, 2006.",
        "year": 2006,
        "date": "2006-02-18",
        "usage_type": "licensed",
        "usage_license_code": "cc_by_sa_3_0",
        "usage_license_name": "Creative Commons Attribution-ShareAlike 3.0",
        "usage_license_url": "https://creativecommons.org/licenses/by-sa/3.0",
        "attributed_name": "Moja~commonswiki",
        "attributed_url": "",
        "source_url": "https://en.wikipedia.org/wiki/Nintendo#/media/File:Nintendo_office.jpg"
      },
      "relationships": {
        "uploaded_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://api.dbljump.com/users/1"
          }
        },
        "place": {
          "data": null
        }
      },
      "links": {
        "self": "http://api.dbljump.com/images/nintendo-office-2006-uncategorized-moja-commonswiki"
      }
    },
    {
      "id": "2",
      "type": "images",
      "attributes": {
        "slug": "mario-figure-2016-uncategorized",
        "file": "url": "https://dbljumpheroku.s3.amazonaws.com/uploads/images/2/mario-figure.jpg",
        "kind": "photo",
        "title": "Mario figure",
        "description": "",
        "year": 2016,
        "date": "2016-07-30",
        "usage_type": "free",
        "usage_license_code": null,
        "usage_license_name": null,
        "usage_license_url": null,
        "attributed_name": null,
        "attributed_url": null,
        "source_url": ""
      },
      "relationships": {
        "uploaded_by": {
          "data": {
            "id": "1",
            "type": "users"
          },
          "links": {
            "related": "http://api.dbljump.com/users/1"
          }
        },
        "place": {
          "data": null
        }
      },
      "links": {
        "self": "http://api.dbljump.com/images/mario-figure-2016-uncategorized"
      }
    }
  ],
  "links": {},
  "meta": {
    "total_items": 2
  }
}
```

Retrieve all images. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /images`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[images]=file,title`
filter[{field}] | All records | Filter search by field, e.g. `?filter[kind]=logo`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
