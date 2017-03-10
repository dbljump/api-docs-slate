## Update an image record

> Request body

```JSON
{
  "data": {
    "type": "images",
    "id": "portrait-of-takashi-tezuka-2017-likeness-jonny-snapper",
    "attributes": {
      "type": "Image::Screen",
      "kind": "gameplay",
      "title": "New Title",
      "description": "New description.",
      "year": "",
      "date": "2000-01-01",
      "place_id": "3",
      "usage_type": "licensed",
      "usage_license_code": "cc_by_3_0",
      "attributed_name": "New Attributed Name",
      "attributed_url": "http://www.new-site.com",
      "source_url": "http://www.new-site/new-file.jpg"
    }
  }
}
```

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
      "source_url": "http://www.new-site/new-file.jpg",
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
        "data": {
          "id": "3",
          "type": "place_countries"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/images/nintendo-office-2006-uncategorized-moja-commonswiki"
    }
  },
  "meta": {
    "keywords": "new title, 2000, 2000-01-01, new attributed name, photo, false, image, picture, media, dbljump, video games, pc games, gaming",
    "description": "'New Title' is a video game image at Dbljump.",
    "created_at": "2017-03-08T17:37:22.384Z",
    "updated_at": "2017-03-08T20:31:44.725Z"
  }
}
```

Update an existing image record. The user must be an editor.

The `file` attribute cannot be updated. A new image file can only be uploaded with a new image record.

* User authentication: required
* Authorization level: editor

### HTTP request

`PATCH /images/'slug'` (replace `slug` with image record slug)

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
type | string | Req'd. Must be 'art', 'doc', 'photo', or 'screen'.
kind | string | Req'd. A subcategory related to the given type. See [Kind](#image_kind).
title | string | Req'd. Max 100 chars.
description | string | Max 250 chars.
year | integer | 1800 to present year.
date | date | 1800-01-01 to present year.
place_id | belongs_to | Must be valid place ID.
usage_type | string | Must be 'free', 'fair', or 'licensed'. See [Usage type](#image_usage_type).
usage_license_code | string | Req'd if usage_type is 'licensed'. See [Usage license](#image_usage_license).
attributed_name | string | Image owner's name. Max 100 chars. Req'd if usage_type is 'licensed'.
attributed_url | string | The owner's website. Max 250 chars.
source_url | string | Req'd if usage_type is 'licensed'. Max 250 chars. URL of image source.

### Success HTTP response code

`200 OK`

### Errors

<aside class="notice">Actual error codes may include the image sub-class, e.g. 'IMAGE_SCREEN_FILE_BLANK'</aside>

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | IMAGE_FILE_ACCEPTED | file | File cannot be updated.
400 | IMAGE_TITLE_BLANK | title | Title is required.
400 | IMAGE_TITLE_TOO_LONG | title | Title cannot be more than 100 characters.
400 | IMAGE_DESCRIPTION_TOO_LONG | description | Description cannot be more than 250 characters.
400 | IMAGE_TYPE_BLANK | type | Type is required.
400 | IMAGE_TYPE_INCLUSION | type | Type must be 'Image::Art', 'Image::Doc', 'Image::Photo' or 'Image::Screen'.
400 | IMAGE_KIND_BLANK | kind | Kind is required.
400 | IMAGE_KIND_INCLUSION | kind | Kind must be a valid value for this image type.
400 | IMAGE_YEAR_INCLUSION | year | Year must be between 1800 and the present year.
400 | IMAGE_DATE_INCLUSION | year | Date must be between 1 January 1800 and the present date.
400 | IMAGE_USAGE_TYPE_BLANK | usage_type | Usage type is required.
400 | IMAGE_USAGE_TYPE_INCLUSION | usage_type | Usage type must be 'free', 'fair', or 'licensed'.
400 | IMAGE_ATTRIBUTED_NAME_BLANK | attributed_name | Attributed name is required if usage type is 'licensed'.
400 | IMAGE_ATTRIBUTED_NAME_TOO_LONG | attributed_name | Attributed name cannot be more than 100 characters.
400 | IMAGE_ATTRIBUTED_URL_TOO_LONG | attributed_url | Attributed URL cannot be more than 250 characters.
400 | IMAGE_SOURCE_URL_BLANK | source_url | Source url is required if usage type is 'licensed'.
400 | IMAGE_SOURCE_URL_TOO_LONG | source_url | Source url cannot be more than 250 characters.
400 | IMAGE_USAGE_LICENSE_CODE_BLANK | usage_license_code | Usage license code is required if usage type is 'licensed'.
400 | IMAGE_USAGE_LICENSE_CODE_INCLUSION | usage_license_code | Usage license code must be valid.
401 | USER_LOGIN_EXPIRED | n/a | The JWT in the header has expired.
401 | USER_UNAUTHORIZED | n/a | The user doesn't have the right permissions, or there's an authentication problem.
