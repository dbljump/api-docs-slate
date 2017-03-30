## <a name="users_update"></a>Update a user account details

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
		"avatar_base64": "data:image/gif;base64,R0lGODlhBQAFAIAAAAAAAP///ywAAAAABQAFAAACBIyPqVgAOw==",
    "remove_avatar": "false"
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
      "avatar": {
        "url": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/4/1703212349.gif"
      },
      "birthday": "1985-07-20",
      "jwt": null
    },
    "relationships": {
      "country": {
        "data": {
          "id": "5",
          "type": "place_countries"
        },
        "links": {
          "related": "http://api.dbljump.com/places/countries/andorra"
        }
      },
      "images": {
        "links": {
          "related": "http://api.dbljump.com/users/4/images"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/users/4"
    }
  },
  "meta": {
    "keywords": "updated_username, updated name, user, dbljump, video games, pc games, gaming",
    "description": "Updated Name is a member at Dbljump, the video game reference.",
    "created_at": "2017-03-21T23:34:55.501Z",
    "updated_at": "2017-03-21T23:49:55.104Z",
    "last_signed_in_at": null,
    "last_sign_in_ip": null,
    "sign_in_count": 0,
    "activated_at": "2017-03-21T23:34:55.419Z"
  }
}
```

Update an existing user account. A user can update their own account. An admin can update any other non-admin account.

Admin-level authorization is required to update attributes role.

* User authentication: required
* Authorization level: Any if editing own account. Admin if editing other user's account. Admin-level accounts can only be edited by the account owner.

### HTTP request

`PATCH /users/{id}` (replace `{id}` with user record ID)

### Request attributes

Attribute | Type | Req'd | Description
--------- | ---- | ----- | -----------
username | string | Y | Must be unique. 2-24 chars. Letters, numbers and underscores only. See [Username](#user_username).
email | string | Y | Must be unique. Max 255 chars. Email format only. Downcased on save. See [Email](#user_email).
role | string | | Authorization level. Defaults to `member`. Can only be updated by admin users. See [Role](#user_role).
password | string | Y | New password. Any 8-24 chars.
password_confirmation | string | Y | Required if changing password. Must match password.
given_names | string |  |Any 1-20 chars.
family_name | string | | Any 1-20 chars.
gender | string | | Any 1-20 chars. Client could suggest 'male' or 'female'.
birthday | date | | Format 'YYYY-MM-DD'. Must not be a future date or > 100 years ago.
country_id | integer | | Must be a valid country record ID.
avatar_base64 | string | | Base64 encoded JPEG, GIF or PNG. Any size (needs review).
remove_avatar | boolean | | Set as true to remove the avatar.

### <a name="user_role"></a>Role

Dbljump has three kinds of users, representing three levels of authorization. They are defined by the value of the `role` attribute, which has three possible values.

Value | Description
----- | -----------
member | Ordinary users who sign up at Dbljump.com. No special privileges.
editor | Can edit and create records. Must complete an approval process.
admin | The highest level of authorization. Can do everything.

### Success HTTP response code

`200 OK`
