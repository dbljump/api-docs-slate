## Delete an image record

Delete an existing image record. An editor can delete images they uploaded. An admin can delete any image.

* User authentication: required
* Authorization level: Editor to delete own images. Admin to delete any image.

### HTTP request

`DELETE /images/{slug}` (replace `{slug}` with image record slug)

### Success HTTP response code

`204 No Content`
