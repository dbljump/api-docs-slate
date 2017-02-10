# Users: authentications

Resources related to user sign-ins.

### JSON web tokens (JWT)

This API uses <a href="https://jwt.io" target="_blank">JSON web tokens (JWT)</a> for authentication. Sessions are not used.

It works like this:

* The client sends a user's credentials to the API, and receives a JWT in the response body.
* The client stores this JWT and sends it in the HTTP Authorization header with each subsequent request.
* When the user signs out, the client stops sending the JWT in the HTTP Authorization header.

### JWT payload

The JWT also has a payload with the following attributes, which the client can decode:

* user_id
* user_role
* expiry
