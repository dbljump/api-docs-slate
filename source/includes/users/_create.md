## <a name="users_create"></a>Register a new user

> Request body

```JSON
{
  "data": {
    "type": "users",
    "attributes": {
      "username": "new_user",
      "email": "new@user.com",
      "password": "password",
      "password_confirmation": "password"
    }
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "5",
    "type": "users",
    "attributes": {
      "email": "new@user.com",
      "username": "new_user",
      "role": "member",
      "given_names": null,
      "family_name": null,
      "gender": null,
      "avatar": null,
      "birthday": null,
      "jwt": null
    },
    "relationships": {
      "country": {
        "data": null,
        "links": {
          "related": "http://api.dbljump.com/places/countries/united-kingdom"
        }
      },
      "images": {
        "links": {
          "related": "http://api.dbljump.com/users/5/images"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/users/5"
    }
  },
  "meta": {
    "keywords": "new_user, new_user, user, dbljump, video games, pc games, gaming",
    "description": "new_user is a member at Dbljump, the video game reference.",
    "created_at": "2017-03-30T12:46:04.648Z",
    "updated_at": "2017-03-30T12:46:05.293Z",
    "last_signed_in_at": null,
    "last_sign_in_ip": null,
    "sign_in_count": 0,
    "activated_at": null
  }
}
```

Create a new user account. No authentication is required. Anyone can sign up for a new account with the default `role` of `member`.

* User authentication: not required
* Authorization level: N/A

### HTTP request

`POST /users`

### Request attributes

Attribute | Type | Req'd | Description
--------- | ---- | ----- | -----------
username | string | Y | Must be unique. 2-24 chars. Letters, numbers and underscores only. See [Username](#user_username).
email | string | Y | Must be unique. Max 255 chars. Email format only. Downcased on save. See [Email](#user_email).
password | string | Y | Any 8-24 chars.
password_confirmation | string | Y | Must match password.

### <a name="user_username"></a>Username

Usernames must be unique, 2-24 chars, and include letters, numbers and underscores only. They must match the following regular expressions.

Language | Regular expression
-------- | ------------------
Ruby | /^[a-zA-Z0-9](\w/&#124;\.)*[a-zA-Z0-9]$/
JavaScript | ^[a-zA-Z0-9](\\w&#124;\\.)*[a-zA-Z0-9]$

### <a name="user_email"></a>Email

Email addresses must be unique, no moe than 255 chars, and be in a valid email format. They must match the following regular expressions.

Language | Regular expression
-------- | ------------------
Ruby | /\A[\w+\-.]+@[a-z\d\-.]+\.[a-z]+\z/i
JavaScript | ^[\\w+\\-.]+@[a-z\\d\\-.]+\\.[a-z]+$

### Success HTTP response code

`201 Created`
