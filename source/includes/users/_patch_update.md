## Update a user account details

> Request body

```JSON
{
 "data": {
	"type": "users",
	"id": "4",
	"attributes": {
		"email": "updated@email.com",
		"username": "updated_username",
		"password": "newpassword",
		"password_confirmation": "newpassword",
		"role": "editor",
		"given_names": "Updated",
		"family_name": "Name",
		"gender": "male",
		"birthday": "1985-07-20",
		"country_id": 5,
		"avatar": "data:image/gif;base64,R0lGODlhBQAFAIAAAAAAAP///ywAAAAABQAFAAACBIyPqVgAOw=="
	}
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "4",
    "type": "users",
    "attributes": {
      "email": "updated@email.com",
      "username": "updated_username",
      "role": "editor",
      "given_names": "Updated",
      "family_name": "Name",
      "gender": "male",
      "avatar": "/uploads/user_avatar/4/1702101051.gif",
      "birthday": "1985-07-20"
    },
    "relationships": {
      "country": {
        "data": {
          "id": "5",
          "type": "place_countries"
        },
        "links": {
          "country": "http://localhost:3000/places/countries/andorra"
        }
      }
    },
    "links": {
      "self": "http://localhost:3000/users/4"
    }
  },
  "meta": {
    "keywords": "updated_username, updated name, user, dbljump, video games, pc games, gaming",
    "description": "Updated Name is a member at Dbljump, the video game reference.",
    "created_at": "2017-01-28T23:19:21.362Z",
    "updated_at": "2017-02-10T10:51:46.844Z",
    "last_signed_in_at": null,
    "last_sign_in_ip": null,
    "sign_in_count": 0,
    "activated_at": "2017-01-28T23:19:21.285Z"
  }
}
```

Update an existing user account. A user can update their own account. An admin can update any other non-admin account.

Admin-level authorization is required to update attributes role.

* User authentication: required
* Authorization level: Any if editing own account. Admin if editing other user's account. Admin-level accounts can only be edited by the account owner.

### HTTP request

`PATCH /users/id` (replace `id` with user record ID)

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
username | string | Required. Must be unique. 2-24 chars. Letters, numbers and underscores only.
email | string | Required. Must be unique. Max 255 chars. Email format only. Downcased on save.
role | string | Authorization level. Must be 'member', 'editor' or 'admin'. Can only be updated by admin users.
password | string | New password. Any 8-24 chars.
password_confirmation | string | Required if changing password. Must match password.
given_names | string | Any 1-20 chars.
family_name | string | Any 1-20 chars.
gender | string | Any 1-20 chars. Client could suggest 'male' or 'female'.
birthday | date | Format 'YYYY-MM-DD'. Must not be a future date or > 100 years ago.
country_id | integer | Must be a valid country record ID.
avatar | string | Base64 encoded JPEG, GIF or PNG. Any size (needs review).

### Success HTTP response code

`200 OK`

### Errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | USER_USERNAME_BLANK | username | Username is required.
400 | USER_USERNAME_INVALID | username | Username can only contain letters, numbers, and underscores.
400 | USER_USERNAME_TAKEN | username | Username has already been taken.
400 | USER_USERNAME_TOO_SHORT | username | Username cannot be less than 2 characters.
400 | USER_USERNAME_TOO_LONG | username | Username cannot be more than 24 characters.
400 | USER_EMAIL_BLANK | email | Email is required.
400 | USER_EMAIL_INVALID | email | Email must be a valid address.
400 | USER_EMAIL_TAKEN | email | Email has already been taken.
400 | USER_EMAIL_TOO_LONG | email | Username cannot be more than 255 characters.
400 | USER_ROLE_INVALID | role | Role must be 'member', 'editor', or 'admin'.
400 | USER_PASSWORD_BLANK | password | Password is required.
400 | USER_PASSWORD_TOO_SHORT | password | Password cannot be less than 8 characters.
400 | USER_PASSWORD_TOO_LONG | password | Password cannot be more than 24 characters.
400 | USER_PASSWORD_CONFIRMATION_CONFIRMATION | password_confirmation | Password and confirmation must match.
400 | USER_GIVEN_NAMES_TOO_LONG | given_names | Given name cannot be more than 20 characters.
400 | USER_FAMILY_NAME_TOO_LONG | family_name | Family name cannot be more than 20 characters.
400 | USER_GENDER_TOO_LONG | gender | Gender cannot be more than 20 characters.
400 | USER_BIRTHDAY_INCLUSION | birthday | Birthday must not be a future date, or over 100 years ago.
400 | USER_COUNTRY_ID_INVALID | country_id | Country must be valid.
401 | USER_LOGIN_EXPIRED | n/a | The JWT in the header has expired.
401 | USER_UNAUTHORIZED | n/a | The user isn't an admin, or there's an authentication problem.
