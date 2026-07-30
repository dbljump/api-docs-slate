# Authentication

## Sign in

> Request

```JSON
POST https://www.dbljump.com/user-authentications

{
  "data": {
    "type": "userAuthentication",
    "attributes": {
      "email": "member@example.com",
      "password": "correct horse battery staple",
      "rememberMe": true
    }
  }
}
```

`POST /user-authentications` signs in an activated user. On success it returns
`200 OK`, a small user resource, and an `Authorization: Bearer {token}`
response header. Store that complete header value and send it with subsequent
authenticated requests.

`rememberMe` defaults to `false` and controls the token lifetime.

## JWT payload

New tokens use the standard `exp` expiry claim and include the user's ID and
role. The server also accepts legacy tokens containing `expiry`.

An invalid token returns `TOKEN_INVALID`; an expired token returns
`TOKEN_EXPIRED`.

## Authentication handoff

Authentication handoffs transfer a signed-in session between Dbljump clients
without exposing the current JWT in a URL.

### Create a handoff

`POST /authentication-handoffs`

Requires a valid bearer token. Returns `201 Created`:

```JSON
{
  "code": "single-use-short-lived-code"
}
```

### Exchange a handoff

> Request

```JSON
POST https://www.dbljump.com/authentication-handoffs/exchange

{
  "code": "single-use-short-lived-code"
}
```

The exchange is unauthenticated. A valid, unused code returns `200 OK`:

```JSON
{
  "authHeader": "Bearer {token}",
  "data": {
    "type": "users",
    "id": "42",
    "attributes": {
      "username": "player",
      "avatarThumb": "https://www.dbljump.com/uploads/user_avatar/42/thumb.jpg"
    }
  }
}
```

Codes expire after five minutes and can be exchanged only once. Both handoff
responses disable caching. Missing, expired, or reused codes return `401`.
