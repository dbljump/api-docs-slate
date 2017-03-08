## Set a new user password

> Request body

```JSON
{
  "data": {
    "type": "user_passwords",
    "id": "Bml5G2MnBqMJVFacD243tffPmKrmnwX",
    "attributes": {
      "email": "user@example.com",
      "password": "new_password",
      "password_confirmation": "new_password"
    }
  }
}
```

A user can set a new password after following a reset-password link. The reset token in the link expires after 2 hours.

* User authentication: not required
* Authorization level: N/A

### HTTP request

`PATCH /users/passwords/'password_reset_token'` (replace `password_reset_token` with the password reset token)

### Request attributes

Attribute | Type | Description
--------- | ---- | -----------
id | string | The password reset token, available in the password reset link URL. Required.
email | string | The user's registered email address, available in the password reset link URL. Required.
password | string | New password. Required. Any 8-24 chars.
password_confirmation | string | Required. Must match password.

### Success HTTP response code

`204 No Content`

### Errors

HTTP code | Error code | Pointer | Title | Detail
--------- | ---------- | ------- | ----- | ------
400 | USER_EMAIL_INVALID | email | User not found. | Invalid email address.
400 | USER_ACTIVATION_REQUIRED | email | User activation required. | User not yet activated.
400 | USER_PASSWORD_TOKEN_INVALID | password_reset_token | Cannot reset user password. | Password reset token invalid.
400 | USER_PASSWORD_TOKEN_EXPIRED | password_reset_token | Cannot reset user password. | Password reset token expired.
400 | USER_PASSWORD_BLANK | password | Password is required.
400 | USER_PASSWORD_TOO_SHORT | password | Password cannot be less than 8 characters.
400 | USER_PASSWORD_TOO_LONG | password | Password cannot be more than 24 characters.
400 | USER_PASSWORD_CONFIRMATION_CONFIRMATION | password_confirmation | Password and confirmation must match.
