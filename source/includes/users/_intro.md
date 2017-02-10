# Users

Resources related to user accounts.

### Mutable attributes

Attribute | Type | Description
--------- | ---- | -----------
username | string | Required. Must be unique. 2-24 chars. Letters, numbers and underscores only.
email | string | Required. Must be unique. Max 255 chars. Email format only. Downcased on save.
role | string | Authorization level. Required. Default: `member`. See 'User roles' below.
avatar | string | User picture. Submissions must be base64 encoded. Must be JPG, GIF or PNG. No size limits.
given_name | string | Any 1-20 chars.
family_name | string | Any 1-20 chars.
gender | string | Any 1-20 chars. Client could suggest 'male' or 'female'.
birthday | date | Format 'YYYY-MM-DD'. Must not be a future date or > 100 years ago.
country_id | integer | Must be a valid country record ID.
avatar | string | Base64 encoded JPEG, GIF or PNG. Any size (needs review).


### User roles

Dbljump has three kinds of users, representing three levels of authorization. They are defined by the value of the `role` attribute, which has three possible values.

Value | Description
----- | -----------
member | Ordinary users who sign up at Dbljump.com. No special privileges.
editor | Can edit and create records. Must complete an approval process.
admin | The highest level of authorization. Can do everything.
