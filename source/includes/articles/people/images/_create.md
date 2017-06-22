## <a name="company_images_create"></a>Upload a new company image

> Request body | `POST /articles/people/shigeru-miyamoto/images`

```JSON
{
  "data": {
    "type": "images",
    "attributes": {
      "base64_file": "data:image/gif;base64,R0lGODlhBQAFAIAAAAAAAP///ywAAAAABQAFAAACBIyPqVgAOw==",
      "kind": "photo",
      "title": "Portrait of Shigeru Miyamoto",
      "description": "Shigeru Miyamoto in Kyoto on 12 April 2012.",
      "year": "",
      "date": "2012-04-12",
      "usage_type": "free",
      "usage_license_code": "",
      "attributed_name": "",
      "attributed_url": "",
      "source_url": ""
    },
    "relationships": {
      "place": {
        "data": {
          "id": "2932",
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
        "id": "7",
        "type": "images",
        "attributes": {
            "kind": "photo",
            "slug": "portrait-of-shigeru-miyamoto-photo",
            "file": "http://localhost:3000/uploads/images/7/file.gif",
            "title": "Portrait of Shigeru Miyamoto",
            "description": "Shigeru Miyamoto in Kyoto on 12 April 2012.",
            "year": 2012,
            "date": "2012-04-12",
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
                    "id": "2",
                    "type": "users"
                },
                "links": {
                    "related": "http://localhost:3000/users/2"
                }
            },
            "place": {
                "data": {
                    "id": "2932",
                    "type": "places"
                },
                "links": {
                    "related": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
                }
            },
            "games": {
                "data": []
            },
            "companies": {
                "data": []
            },
            "people": {
                "data": [
                    {
                        "id": "21",
                        "type": "people"
                    }
                ]
            },
            "game_versions": {
                "data": []
            }
        },
        "links": {
            "self": "http://localhost:3000/media/images/portrait-of-shigeru-miyamoto-photo"
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
                "avatar": "http://localhost:3000/uploads/user_avatar/2/1706221451.jpg"
            },
            "links": {
                "self": "http://localhost:3000/users/2"
            }
        },
        {
            "id": "2932",
            "type": "places",
            "attributes": {
                "kind": "locality",
                "slug": "kyoto-kyoto-prefecture-japan",
                "name": "Kyoto",
                "formatted": "Kyoto, Kyoto Prefecture, Japan",
                "short_name": null
            },
            "links": {
                "self": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
            }
        },
        {
            "id": "21",
            "type": "people",
            "attributes": {
                "display_title": "Shigeru Miyamoto"
            },
            "links": {
                "self": "http://localhost:3000/articles/people/shigeru-miyamoto"
            }
        }
    ],
    "meta": {
        "keywords": "Portrait of Shigeru Miyamoto, photo, 2012, 2012-04-12, image, picture, media, dbljump, video games, pc games, gaming",
        "description": "'Portrait of Shigeru Miyamoto' is a video game image at Dbljump.",
        "created_at": "2017-06-22T15:17:48.517Z",
        "updated_at": "2017-06-22T15:17:48.517Z"
    }
}
```

Upload a new image associated with a given person article. User must be an editor or admin.

* User authentication: required
* Authorization level: editor

### HTTP request

`POST /articles/people/{person-id}/images` (replace `person-id` with person ID or slug)

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

If `usage_type` is set to `licensed`, a valid image license code must be provided. Please see [Media Image Licenses](#media_licenses_intro).

### Success HTTP response code

`201 Created`
