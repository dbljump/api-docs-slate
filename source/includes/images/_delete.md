## Delete an image record

Delete an existing image record. An editor can delete images they uploaded. An admin can delete any image.

* User authentication: required
* Authorization level: Editor to delete own images. Admin to delete any image.

### HTTP request

`DELETE /images/'slug'` (replace `slug` with image record slug)

### Success HTTP response code

`204 No Content`

### Errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
401 | USER_LOGIN_EXPIRED | n/a | The JWT in the header has expired.
401 | USER_UNAUTHORIZED | n/a | The user isn't an admin, or there's an authentication problem.
404 | RECORD_NOT_FOUND | n/a | Record not found. |
