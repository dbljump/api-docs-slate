## Errors

Errors specific to creating and updating image records.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | IMAGE_BASE64_FILE_BLANK | base64_file | File is required.
400 | IMAGE_BASE64_FILE_PRESENT | base64_file | Base64 file is not accepted for this action.
400 | IMAGE_TITLE_BLANK | title | Title is required.
400 | IMAGE_TITLE_TOO_LONG | title | Title cannot be more than 100 characters.
400 | IMAGE_DESCRIPTION_TOO_LONG | description | Description cannot be more than 250 characters.
400 | IMAGE_SUBTYPE_BLANK | type | Subtype is required.
400 | IMAGE_SUBTYPE_INCLUSION | type | Subtype must be 'artworks', 'docs', 'photos' or 'screens'.
400 | IMAGE_KIND_BLANK | kind | Kind is required.
400 | IMAGE_KIND_INCLUSION | kind | Kind must be a valid value for this image type.
400 | IMAGE_YEAR_INCLUSION | year | Year must be between 1800 and the present year.
400 | IMAGE_DATE_INCLUSION | year | Date must be between 1 January 1800 and the present date.
400 | IMAGE_USAGE_TYPE_BLANK | usage_type | Usage type is required.
400 | IMAGE_USAGE_TYPE_INCLUSION | usage_type | Usage type must be 'free', 'fair', or 'licensed'.
400 | IMAGE_ATTRIBUTED_NAME_BLANK | attributed_name | Attributed name is required if usage type is 'licensed'.
400 | IMAGE_ATTRIBUTED_NAME_TOO_LONG | attributed_name | Attributed name cannot be more than 100 characters.
400 | IMAGE_ATTRIBUTED_URL_TOO_LONG | attributed_url | Attributed URL cannot be more than 250 characters.
400 | IMAGE_SOURCE_URL_BLANK | source_url | Source url is required if usage type is 'licensed'.
400 | IMAGE_SOURCE_URL_TOO_LONG | source_url | Source url cannot be more than 250 characters.
400 | IMAGE_USAGE_LICENSE_CODE_BLANK | usage_license_code | Usage license code is required if usage type is 'licensed'.
400 | IMAGE_USAGE_LICENSE_CODE_INCLUSION | usage_license_code | Usage license code must be valid.
