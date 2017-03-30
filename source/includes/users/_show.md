## <a name="users_show"></a>Get single user

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "2",
    "type": "users",
    "attributes": {
      "email": "neil@example.com",
      "username": "neil",
      "role": "admin",
      "given_names": "Neil",
      "family_name": "Wheatley",
      "gender": "male",
      "avatar": {
        "url": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1703212334.jpg"
      },
      "birthday": "1980-02-14",
      "jwt": null
    },
    "relationships": {
      "country": {
        "data": {
          "id": "219",
          "type": "place_countries"
        },
        "links": {
          "related": "http://api.dbljump.com/places/countries/united-kingdom"
        }
      },
      "images": {
        "links": {
          "related": "http://api.dbljump.com/users/2/images"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/users/2"
    }
  },
  "meta": {
    "keywords": "neil, neil wheatley, user, dbljump, video games, pc games, gaming",
    "description": "Neil Wheatley is a member at Dbljump, the video game reference.",
    "created_at": "2017-03-21T23:34:54.651Z",
    "updated_at": "2017-03-21T23:47:14.034Z",
    "last_signed_in_at": "2017-03-21T23:47:13.936Z",
    "last_sign_in_ip": "94.4.193.77",
    "sign_in_count": 1,
    "activated_at": "2017-03-21T23:34:53.917Z"
  }
}
```

Retrieve a single existing user account record. Any user can retrive their own account. An admin-level user can retrieve any user account.

* User authentication: required
* Authorization level: Any, if retrieving own account. Admin if retriveing other user's account.

### HTTP request

`GET /users/{id}` (replace `{id}` with user record ID)

### Success HTTP response code

`200 OK`

### <a name="user_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
email | string | Y | The user's registered email address.
username | string | Y | The user's registered username.
role | string | Y | Authorization role. Can be `member`, `editor` or `admin`. See [Role](#user_role).
given_names | string | | The user's given names, e.g. 'Jean Pierre'.
family_name | string | | The user's family name, e.g. 'Blanc'.
gender | string | | Usually `male` or `female`, but can be any string.
avatar/url | string | | URL of the user's avatar image.
birthday | date | | E.g. '1977-12-19'
jwt | string | | Always `null` for this endpoint.

### Relationships

Association | Record type | Relationship type
----------- | ----------- | -----------------
country | places(countries) | belongs_to
images | images | has_many

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
places(countries) | country | subtype, slug, name, short_name, formatted

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at`, `updated_at`, `last_signed_in_at`, `last_sign_in_ip`, `sign_in_count` and `activated_at` attributes.
