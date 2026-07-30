# Users

## User resources

`/users` uses type `user`.

Method | Path | Authorization
------ | ---- | -------------
GET | `/users` | Public
GET | `/users/{id}` | Public
POST | `/users` | Public registration
PATCH | `/users/{id}` | Same user or admin
DELETE | `/users/{id}` | Same user, or admin deleting a non-admin

### Registration

Writable registration fields are `email`, `username`, `password`,
`passwordConfirmation`, `acceptedTerms`, and `editorRequest`.

Email must be valid and unique. Username must be unique, contain only letters,
numbers, underscores, or dots, begin and end with a letter or number, and be
2–12 characters. Password must be 8–24 characters. Terms acceptance is
required.

Registration returns `201 Created` and sends an activation email.

### Updating a user

A user or admin can write `unconfirmedEmail`, `username`, `acceptedTerms`,
`base64Image`, `removeAvatar`, `givenNames`, `familyName`, `gender`,
`birthday`, `place`, `password`, and `passwordConfirmation`.

Only admins can also write `role` and `editorRequestApproved`. Roles are
`member`, `editor`, and `admin`.

Email and administrative metadata are returned only to the same user or an
admin. Public responses include `username`, `role`, names, `gender`,
`birthday`, `avatar`, `avatarThumb`, and `place`.

Queryable fields are `id`, `username`, `gender`, `role`, `placeId`,
`editorRequestOpen`, `lastSignedInAt`, `activatedAt`, `birthday`,
`lastActiveAt`, `createdAt`, and `updatedAt`.

## Account activation

`POST /user-activations` activates an account using `email` and
`activationToken`. It returns the activated user with `200 OK`.

`PATCH /user-activations` requests a replacement activation email using
`email`. It returns `204 No Content`.

Both operations are unauthenticated.

## Email confirmation

`POST /email-confirmations` confirms a pending email-address change. Send
`unconfirmedEmail` and `confirmToken` in a JSON:API document. The user must
already be activated. Success returns the updated user with `200 OK`.

## Password reset

`POST /user-passwords` requests a password-reset email. Send `email`; success
returns `204 No Content`.

`PATCH /user-passwords` completes the reset. Send `email`, `password`, and
`passwordResetToken`; success returns `204 No Content`.

Both password operations are unauthenticated.
