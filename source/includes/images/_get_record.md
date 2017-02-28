## Get single image

> HTTP 200 response body

```JSON

```

Retrieve a single image record. Images are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /images/'slug'` (replace `slug` with image record slug)

### Success HTTP response code

`200 OK`

### Errors

HTTP code | Error code | Pointer | Title | Description
--------- | ---------- | ------- | ----- | -----------
404 | RECORD_NOT_FOUND | n/a | Record not found. |
