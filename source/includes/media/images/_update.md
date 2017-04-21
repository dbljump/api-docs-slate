## <a name="images_update"></a>Update an image record

> Request body | `PATCH /media/images/nintendo-office-photo`

```JSON
{
  "data": {
    "type": "images",
    "id": "portrait-of-takashi-tezuka-2017-likeness-jonny-snapper",
    "attributes": {
      "kind": "screen",
      "title": "New Title",
      "description": "New description.",
      "year": "",
      "date": "2000-01-01",
      "usage_type": "licensed",
      "usage_license_code": "cc_by_3_0",
      "attributed_name": "New Attributed Name",
      "attributed_url": "http://www.new-site.com",
      "source_url": "http://www.new-site/new-file.jpg"
    },
    "relationships": {
      "country": {
        "data": {
          "id": "3",
          "type": "places"
        }
      }
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
  "data": {
    "id": "1",
    "type": "images",
    "attributes": {
      "kind": "screen",
      "slug": "new-title-screen",
      "file": "https://dbljumpheroku.s3.amazonaws.com/uploads/images/1/nintendo-hq-kyoto-2006.jpg",
      "title": "New Title",
      "description": "New description.",
      "year": 2000,
      "date": "2000-01-01",
      "usage_type": "licensed",
      "usage_license_code": "cc_by_3_0",
      "usage_license_name": "Creative Commons Attribution 3.0",
      "usage_license_url": "https://creativecommons.org/licenses/by/3.0/",
      "attributed_name": "New Attributed Name",
      "attributed_url": "http://www.new-site.com",
      "source_url": "http://www.new-site/new-file.jpg"
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
        "data": null,
        "links": {
          "related": "http://api.dbljump.com/places/afghanistan"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/media/images/new-title-screen"
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
    "keywords": "new title, screen, 2000, 2000-01-01, new attributed name, image, picture, media, dbljump, video games, pc games, gaming",
    "description": "'New Title' is a video game image at Dbljump.",
    "created_at": "2017-04-21T09:27:46.355Z",
    "updated_at": "2017-04-21T09:34:24.055Z"
  }
}
```

Update an existing image record. The user must be an editor.

The `file` attribute cannot be updated. A new image file can only be uploaded with a new image record.

* User authentication: required
* Authorization level: editor

### HTTP request

`PATCH /media/images/{slug}` (replace `{slug}` with image record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
kind | string | Y | See [Kind](#image_kind).
title | string | Y | Max 100 chars.
description | string | | Max 250 chars.
year | integer | | 1800 to present year.
date | date | | 1800-01-01 to present year.
usage_type | string | Y | Must be 'free', 'fair', or 'licensed'. See [Usage type](#image_usage_type).
usage_license_code | string | * | Req'd if usage_type is 'licensed'. See [Usage license](#image_usage_license).
attributed_name | string | * | Image owner's name. Max 100 chars. Req'd if usage_type is 'licensed'.
attributed_url | string | | The owner's website. Max 250 chars.
source_url | string | * | Req'd if usage_type is 'licensed'. Max 250 chars. URL of image source.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | ----------
place | belongs_to | | places | A [place record](#places_intro) the image is associated with.

### Success HTTP response code

`200 OK`
