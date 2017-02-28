## Update an image record

> Request body

```JSON
{
  "data": {
    "type": "images",
    "id": "portait-of-takashi-tezuka-2017-02-02"
    "attributes": {
      "type": "photo",
      "kind": "likeness",
      "title": "Portrait of Takashi Tezuka",
      "description": "Takashi Tezuka in Kyoto on 4th February 2017.",
      "year": "2017",
      "date": "2017-02-04",
      "place_id": "2932",
      "usage_type": "licensed",
      "usage_license": "cc_by_4_0",
      "attributed_name": "Jonny Snapper",
      "attributed_url": "http://www.jonnys-game-pics.com",
      "source_url": "http://www.jonnys-game-pics.com/tezuka.jpg"
    }
  }
}
```

> HTTP 200 response body

```JSON

```

Update an existing image record account. The user must be an editor.

The `file` attribute cannot be updated. A new image file can only be uploaded with a new image record.

* User authentication: required
* Authorization level: Editor.

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
usage_license | string | Req'd if usage_type is 'licensed'. See [Usage license](#image_usage_license).
attributed_name | string | Image owner's name. Max 100 chars. Req'd if usage_type is 'licensed'.
attributed_url | string | The owner's website. Max 250 chars.
source_url | string | Req'd if usage_type is 'licensed'. Max 250 chars. URL of image source.

### Success HTTP response code

`200 OK`

### Errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
401 | USER_LOGIN_EXPIRED | n/a | The JWT in the header has expired.
401 | USER_UNAUTHORIZED | n/a | The user doesn't have the right permissions, or there's an authentication problem.
404 | RECORD_NOT_FOUND | n/a | Record not found. |
