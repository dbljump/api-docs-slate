## Upload a new image

> Request body

```JSON
{
  "data": {
    "type": "images",
    "attributes": {
      "file": "data:image/gif;base64,R0lGODlhBQAFAIAAAAAAAP///ywAAAAABQAFAAACBIyPqVgAOw==",
      "type": "Image::Photo",
      "kind": "likeness",
      "title": "Portrait of Takashi Tezuka",
      "description": "Takashi Tezuka in Kyoto on 2nd February 2017.",
      "year": "",
      "date": "2017-02-02",
      "place_id": "1",
      "usage_type": "licensed",
      "usage_license_code": "cc_by_4_0",
      "attributed_name": "Jonny Snapper",
      "attributed_url": "http://www.jonnys-game-pics.com",
      "source_url": "http://www.jonnys-game-pics.com/tezuka.jpg"
    }
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "5",
    "type": "image_photos",
    "attributes": {
      "file": "/uploads/images/5/file.gif",
      "type": "Image::Photo",
      "kind": "likeness",
      "title": "Portrait of Takashi Tezuka",
      "description": "Takashi Tezuka in Kyoto on 2nd February 2017.",
      "year": 2017,
      "date": "2017-02-02",
      "usage_type": "licensed",
      "usage_license_code": "cc_by_4_0",
      "usage_license_name": "Creative Commons Attribution 4.0",
      "usage_license_url": "https://creativecommons.org/licenses/by/4.0",
      "attributed_name": "Jonny Snapper",
      "attributed_url": "http://www.jonnys-game-pics.com",
      "source_url": "http://www.jonnys-game-pics.com/tezuka.jpg",
      "slug": "portrait-of-takashi-tezuka-2017-likeness-jonny-snapper"
    },
    "relationships": {
      "uploaded_by": {
        "data": {
          "id": "2",
          "type": "users"
        }
      },
      "place": {
        "data": {
          "id": "1",
          "type": "place_countries"
        }
      }
    },
    "links": {
      "self": "http://localhost:3000/images/portrait-of-takashi-tezuka-2017-likeness-jonny-snapper"
    }
  },
  "meta": {
    "keywords": "portrait of takashi tezuka, 2017, 2017-02-02, jonny snapper, photo, likeness, image, picture, media, dbljump, video games, pc games, gaming",
    "description": "'Portrait of Takashi Tezuka' is a video game image at Dbljump.",
    "created_at": "2017-03-03T22:37:34.198Z",
    "updated_at": "2017-03-03T22:37:34.198Z"
  }
}
```

Upload a new image. User must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /images`

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
file | string (base64) | Image file encoded as base64. Req'd. See [File](#image_file).
type | string | Req'd. Must be 'Image::Art', 'Image::Doc', 'Image::Photo', or 'Image::Screen'.
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

`201 Created`

### Errors

<aside class="notice">Actual error codes may include the image sub-class, e.g. 'IMAGE_SCREEN_FILE_BLANK'</aside>

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | IMAGE_FILE_BLANK | file | File is required.
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
