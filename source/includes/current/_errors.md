# Errors

JSON:API errors are returned in an `errors` array.

> Validation error

```JSON
{
  "errors": [
    {
      "status": 422,
      "code": "blank",
      "source": {
        "pointer": "/data/attributes/displayTitle"
      },
      "title": "can't be blank"
    }
  ]
}
```

Status | Meaning
------ | -------
400 | Malformed or incomplete request data.
401 | Missing/invalid authentication or insufficient authorization.
404 | Record not found.
409 | Request resource identity conflicts with the URL.
422 | Validation failed or the request is semantically invalid.
500 | Mailer or other server-side operation failed.

Common application codes include `BAD_REQUEST`, `REQUEST_DATA_MISSING`,
`NOT_AUTHORIZED`, `TOKEN_INVALID`, `TOKEN_EXPIRED`,
`USER_CREDENTIALS_INVALID`, `USER_ACTIVATION_REQUIRED`,
`USER_ALREADY_ACTIVATED`, `INVALID_NOTE_ORDER`, `RESOURCE_MISMATCH`,
`MAILER_ERROR`, and `SERVER_ERROR`.

Validation error pointers use lower camel case and point to either
`/data/attributes/{name}` or `/data/relationships/{name}`.
