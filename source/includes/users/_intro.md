# Users

Resources related to user accounts.

### Mutable attributes

Attribute | Type | Description
--------- | ---- | -----------
username | string | Required. Must be unique. 2-24 chars. Letters, numbers and underscores only.
email | string | Required. Must be unique. Max 255 chars. Email format only. Downcased on save.
role | string | Authorization level. Required. Default: `member`. See 'User roles' below.
avatar | string | User picture. Submissions must be base64 encoded. Must be JPG, GIF or PNG. No size limits.
given_name | string | Usually the user's first name. Max 20 chars.
family_name | string | Usually the user's last name. Max 20 chars.
country_id | integer | Dbljump record ID of the user's home country. Must be a valid country ID.
birthday | date | The user's date of birth. Must be less than 110 years ago.
gender | string | Max 20 chars. Form inputs could suggest 'Male' or 'Female' but accept any value.


### User roles

Dbljump has three kinds of users, representing three levels of authorization. They are defined by the value of the `role` attribute, which has three possible values.

Value | Description
----- | -----------
member | Ordinary users who sign up at Dbljump.com. No special privileges.
editor | Can edit and create records. Must complete an approval process.
admin | The highest level of authorization. Can do everything.
