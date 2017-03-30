# Users: authentications

Resources related to user sign-ins.

### JSON web tokens (JWT)

This API uses stateless <a href="https://jwt.io" target="_blank">JSON web tokens (JWT)</a> for authentication. Sessions are not used.

It works like this:

1. The client sends a user's valid credentials to the API, and receives a JWT in the response body.
2. The client stores this JWT and sends it in the HTTP `Authorization` header with each subsequent request.
3. To sign out the user, the client simply stops sending the JWT in the HTTP `Authorization` header.

### JWT payload

The JWT has a payload with the following attributes, which the client can decode:

Attribute | Description
--------- | -----------
user_id | The user record ID.
user_role | Used for authorization. Can be `member`, `editor` or `admin`. Also see [Role](#user_role).
expiry | Date and time of expiry.
