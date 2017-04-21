## <a name="images_create"></a>Upload a new image

> Request body | `POST /media/images`

```JSON
{
  "data": {
    "type": "images",
    "attributes": {
      "base64_file": "data:image/gif;base64,R0lGODlhBQAFAIAAAAAAAP///ywAAAAABQAFAAACBIyPqVgAOw==",
      "kind": "photo",
      "title": "Portrait of Takashi Tezuka",
      "description": "Takashi Tezuka in Kyoto on 2nd February 2017.",
      "year": "",
      "date": "2017-02-02",
      "usage_type": "licensed",
      "usage_license_code": "cc_by_4_0",
      "attributed_name": "Jonny Snapper",
      "attributed_url": "http://www.jonnys-game-pics.com",
      "source_url": "http://www.jonnys-game-pics.com/tezuka.jpg"
    },
    "relationships": {
      "place": {
        "data": {
          "id": "1",
          "type": "places"
        }
      }
    }
  }
}
```

> Response body | `HTTP 201`

```JSON
{
  "data": {
    "id": "3",
    "type": "images",
    "attributes": {
      "kind": "photo",
      "slug": "portrait-of-takashi-tezuka-photo",
      "file": "https://dbljumpheroku.s3.amazonaws.com/uploads/images/3/file.gif",
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
      "source_url": "http://www.jonnys-game-pics.com/tezuka.jpg"
    },
    "relationships": {
      "uploaded_by": {
        "data": {
          "id": "2",
          "type": "users"
        },
        "links": {
          "related": "http://api.dbljump.com/users/2"
        }
      },
      "place": {
        "data": {
          "id": "1",
          "type": "places"
        },
        "links": {
          "related": "http://api.dbljump.com/places/afghanistan"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/media/images/portrait-of-takashi-tezuka-photo"
    }
  },
  "included": [
    {
      "id": "2",
      "type": "users",
      "attributes": {
        "username": "neil",
        "role": "admin",
        "given_names": "Neil",
        "family_name": "Wheatley",
        "avatar": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1704210927.jpg"
      },
      "links": {
        "self": "http://api.dbljump.com/users/2"
      }
    },
    {
      "id": "1",
      "type": "places",
      "attributes": {
        "kind": "country",
        "slug": "afghanistan",
        "name": "Afghanistan",
        "formatted": "Afghanistan",
        "short_name": null
      },
      "links": {
        "self": "http://api.dbljump.com/places/afghanistan"
      }
    }
  ],
  "meta": {
    "keywords": "portrait of takashi tezuka, photo, 2017, 2017-02-02, jonny snapper, image, picture, media, dbljump, video games, pc games, gaming",
    "description": "'Portrait of Takashi Tezuka' is a video game image at Dbljump.",
    "created_at": "2017-04-21T09:32:01.323Z",
    "updated_at": "2017-04-21T09:32:01.323Z"
  }
}
```

Upload a new image. User must be an editor or admin.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /media/images`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
base64_file | string | Y | Image file encoded as base64. See [File](#image_file).
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

### <a name="image_file"></a>File

**File type:** File uploads must be of type GIF, JPG/JPEG, or PNG.

**Base64:** Image file uploads are handled by the Ruby gems [CarrierWave](https://github.com/carrierwaveuploader/carrierwave) and [Carrierwave::Base64](https://github.com/lebedev-yury/carrierwave-base64). Base64 strings should have [the correct data format](https://github.com/lebedev-yury/carrierwave-base64#data-format), i.e.:

`data:image/jpeg;base64,(base64 encoded data)`

### <a name="image_kind"></a>Kind

The `kind` attribute accepts the following values.

Kind | Description
---- | -----------
artwork | Miscellaneous artwork, e.g. production design drawings or promotional art
boxart | Official box art from various regions
doc | Image of a document, e.g. a leaked presentation slide
logo | Usually a company or game logo
photo | A photograph
poster | A game poster
screen  | A screenshot from a game


### <a name="image_usage_type"></a>Usage type

Users should only upload images that can legally be shown on Dbljump.com. An image must therefore have one of three `usage_type` values.

Usage type | usage_type value | Description
---------- | ---------------- | -----------
Free | free | The image is in the public domain and free to use without attribution.
Fair use | fair | The image can be used under US fair use law. May include logos, box-arts, and screenshots.
Licensed | licensed | The image is free to use with some-rights-reserved license, e.g. Creative Commons.

### <a name="image_usage_license"></a>Usage license attribute

If `usage_type` is set to `licensed`, a valid image license code must be provided. Acceptable values are below. We could add an API endpoint to retrieve all these values, such as `/media-licenses`.

usage_license_code | License name | License URL
------------------ | ------------ | -----------
cc_by_2_0 | Creative Commons Attribution 2.0 | https://creativecommons.org/licenses/by/2.0
cc_by_2_5 | Creative Commons Attribution 2.5 | https://creativecommons.org/licenses/by/2.5/
cc_by_sa_2_0 | Creative Commons Attribution-ShareAlike 2.0 | https://creativecommons.org/licenses/by-sa/2.0
cc_by_nd_2_0 | Creative Commons Attribution-NoDerivs 2.0 | http://creativecommons.org/licenses/by-nd/2.0/
cc_by_3_0 | Creative Commons Attribution 3.0 | https://creativecommons.org/licenses/by/3.0/
cc_by_sa_3_0 | Creative Commons Attribution-ShareAlike 3.0 | https://creativecommons.org/licenses/by-sa/3.0
cc_by_nd_3_0 | Creative Commons Attribution-NoDerivs 3.0 | http://creativecommons.org/licenses/by-nd/3.0
cc_by_4_0 | Creative Commons Attribution 4.0 | https://creativecommons.org/licenses/by/4.0
cc_by_sa_4_0 | Creative Commons Attribution-ShareAlike 4.0 | https://creativecommons.org/licenses/by-sa/4.0
cc_by_nd_4_0 | Creative Commons Attribution-NoDerivs 4.0 | http://creativecommons.org/licenses/by-nd/4.0

### Success HTTP response code

`201 Created`
