## Get single image

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "1",
    "type": "image_photos",
    "attributes": {
      "file": "/uploads/images/1/nintendo-hq-kyoto-2006.jpg",
      "type": "Image::Photo",
      "kind": "uncategorized",
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
      "source_url": "https://en.wikipedia.org/wiki/Nintendo#/media/File:Nintendo_office.jpg",
      "slug": "portrait-of-takashi-tezuka-2017-likeness-jonny-snapper"
    },
    "relationships": {
      "uploaded_by": {
        "data": {
          "id": "1",
          "type": "users"
        }
      },
      "place": {
        "data": null
      }
    },
    "links": {
      "self": "http://localhost:3000/images/nintendo-office-2006-uncategorized-moja-commonswiki"
    }
  },
  "meta": {
    "keywords": "nintendo office, 2006, 2006-02-18, moja~commonswiki, photo, false, image, picture, media, dbljump, video games, pc games, gaming",
    "description": "'Nintendo office' is a video game image at Dbljump.",
    "created_at": "2017-03-03T20:01:29.551Z",
    "updated_at": "2017-03-03T20:01:29.551Z"
  }
}
```

Retrieve a single image record. Images are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /images/'slug'` (replace `slug` with image record slug)

### Success HTTP response code

`200 OK`

### Errors

HTTP code | Error code | Pointer | Title | Description
--------- | ---------- | ------- | ----- | -----------
404 | RECORD_NOT_FOUND | n/a | Record not found. |
