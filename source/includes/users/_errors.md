## Errors

Errors specific to registering, updating and authenticating user accounts.

### POST and PATCH errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | USER_USERNAME_BLANK | username | Username is required.
400 | USER_USERNAME_INVALID | username | Username can only contain letters, numbers, and underscores.
400 | USER_USERNAME_TAKEN | username | Username has already been taken.
400 | USER_USERNAME_TOO_SHORT | username | Username cannot be less than 2 characters.
400 | USER_USERNAME_TOO_LONG | username | Username cannot be more than 24 characters.
400 | USER_EMAIL_BLANK | email | Email is required.
400 | USER_EMAIL_INVALID | email | Email must be a valid address.
400 | USER_EMAIL_TAKEN | email | Email has already been taken.
400 | USER_EMAIL_TOO_LONG | email | Username cannot be more than 255 characters.
400 | USER_ROLE_INVALID | role | Role must be 'member', 'editor', or 'admin'.
400 | USER_PASSWORD_BLANK | password | Password is required.
400 | USER_PASSWORD_TOO_SHORT | password | Password cannot be less than 8 characters.
400 | USER_PASSWORD_TOO_LONG | password | Password cannot be more than 24 characters.
400 | USER_PASSWORD_CONFIRMATION_CONFIRMATION | password_confirmation | Password and confirmation must match.
400 | USER_GIVEN_NAMES_TOO_LONG | given_names | Given name cannot be more than 20 characters.
400 | USER_FAMILY_NAME_TOO_LONG | family_name | Family name cannot be more than 20 characters.
400 | USER_GENDER_TOO_LONG | gender | Gender cannot be more than 20 characters.
400 | USER_BIRTHDAY_INCLUSION | birthday | Birthday must not be a future date, or over 100 years ago.
400 | USER_COUNTRY_ID_INVALID | country_id | Country must be valid.
400 | USER_BASE64_FILE_INVALID | base64_file | Base64 file must be in the correct format.

### Authentication errors

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
401 | USER_CREDENTIALS_INVALID | - | User not authorized.
