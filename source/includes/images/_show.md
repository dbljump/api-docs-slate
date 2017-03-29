## <a name="images_show"></a>Get single image

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "1",
    "type": "image_photos",
    "attributes": {
      "file": "https://dbljumpheroku.s3.amazonaws.com/uploads/images/1/nintendo-hq-kyoto-2006.jpg",
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
      "slug": "nintendo-office-2006-uncategorized-moja-commonswiki"
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
      "self": "http://api.dbljump.com/images/nintendo-office-2006-uncategorized-moja-commonswiki"
    }
  },
  "meta": {
    "keywords": "nintendo office, 2006, 2006-02-18, moja~commonswiki, photo, false, image, picture, media, dbljump, video games, pc games, gaming",
    "description": "'Nintendo office' is a video game image at Dbljump.",
    "created_at": "2017-03-08T17:37:22.384Z",
    "updated_at": "2017-03-08T17:37:22.384Z"
  }
}
```

Retrieve a single image record. Images are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /images/{slug}` (replace `{slug}` with image record slug)

### Success HTTP response code

`200 OK`

### <a name="image_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
file/url | string | Y | Image URL, usually at AWS.
subtype | string | Y | The image subclass. Either 'artworks', 'docs', 'photos', or 'screens'.
slug | string | Y | A record ID based on metadata, e.g. 'photo-of-hideo-kojima'.
kind | string | Y | A further subcategory related to subtype. See [Kind](#image_kind).
title | string | Y | The image title.
description | string | | The image description.
year | integer | | Year the image was created.
date | date | | Date the image was created.
usage_type | string | Y | One of three usage types:'free', 'fair', or 'licensed'. See [Usage type](#image_usage_type).
usage_license_code | string | * | Req'd if usage_type is 'licensed'. See [Usage license](#image_usage_license) section.
attributed_name | string | * | The image owner's name. Always present if usage_type is 'licensed'.
attributed_url | string | | The image owner's website URL.
source_url | string | * | The URL the image was sourced from. Always present if usage_type is 'licensed'.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
uploaded_by | users | belongs_to |
place | places | belongs_to

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | uploaded_by | username, role, given_names, family_name, avatar
places | place | subtype, slug, name, short_name, formatted

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
