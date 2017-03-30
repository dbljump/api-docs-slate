## <a name="images_show"></a>Get single image

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "2",
    "type": "images",
    "attributes": {
      "subtype": "photos",
      "slug": "mario-figure-2016-uncategorized",
      "file": {
        "url": "https://dbljumpheroku.s3.amazonaws.com/uploads/images/2/mario-figure.jpg"
      },
      "kind": "uncategorized",
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
        "avatar": {
          "url": null
        }
      },
      "links": {
        "self": "http://api.dbljump.com/users/1"
      }
    }
  ],
  "meta": {
    "keywords": "mario figure, 2016, 2016-07-30, photo, image, picture, media, dbljump, video games, pc games, gaming",
    "description": "'Mario figure' is a video game image at Dbljump.",
    "created_at": "2017-03-30T12:40:13.387Z",
    "updated_at": "2017-03-30T12:40:13.387Z"
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
