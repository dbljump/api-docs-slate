# <a name="images_intro"></a>Images

Resources related to images.

An image record includes the URL of an image stored on Amazon S3, plus metadata about the image. An image can be associated with many articles.

### <a name="image_attrs"></a>Mutable attributes

Attribute | Type | Description
--------- | ---- | -----------
file | string (base64) | Image file encoded as base64. Req'd. See [File](#image_file) section below.
type | string | Req'd. Must be 'art', 'doc', 'photo', or 'screen'.
kind | string | Req'd. A subcategory related to the given type. See [Kind](#image_kind) section below.
title | string | Req'd. Max 100 chars.
description | string | Max 250 chars.
year | integer | 1800 to present year.
date | date | 1800-01-01 to present year.
place_id | belongs_to | Must be valid place ID.
usage_type | string | Must be 'free', 'fair', or 'licensed'. See [Usage type](#image_usage_type) section.
usage_license_code | string | Req'd if usage_type is 'licensed'. See [Usage license](#image_usage_license) section.
attributed_name | string | Image owner's name. Max 100 chars. Req'd if usage_type is 'licensed'.
attributed_url | string | The owner's website. Max 250 chars.
source_url | string | Req'd if usage_type is 'licensed'. Max 250 chars. URL of image source.

### <a name="image_file"></a>File

**File type:** File uploads must be of type GIF, JPG/JPEG, or PNG.

**Base64:** Image file uploads are handled by the Ruby gems [CarrierWave](https://github.com/carrierwaveuploader/carrierwave) and [Carrierwave::Base64](https://github.com/lebedev-yury/carrierwave-base64). If the image is encoded as Base64, it should have [the correct data format](https://github.com/lebedev-yury/carrierwave-base64#data-format), i.e.:

`data:image/jpeg;base64,(base64 encoded data)`

### <a name="image_kind"></a>Kind

The `kind` attribute is a subcategory of `type`. Acceptable values are shown below.

Type | Acceptable kind values
---- | ----------------------
art | boxart, logo, poster, production, uncategorized
doc | publication, slides, text, uncategorized
photo | event, likeness, place, product, uncategorized
screen | credits, gameplay, title, uncategorized

### <a name="image_usage_type"></a>Usage type

Users should only upload images that can legally be shown on Dbljump.com. An image must therefore have one of three `usage_type` values.

Usage type | usage_type value | Description
---------- | ---------------- | -----------
Free | free | The image is in the public domain.
Fair use | fair | The image can be used under US fair use law.
Licensed | licensed | The image is free to use with some-rights-reserved license, e.g. Creative Commons.

### <a name="image_usage_license"></a>Usage license

If `usage_type` is set to `licensed`, a valid image license code must be provided. Acceptable values are below.

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
