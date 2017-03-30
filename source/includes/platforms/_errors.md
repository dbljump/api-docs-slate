## Errors

Errors specific to creating and updating platform records.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | PLATFORM_NAME_BLANK | name | Name is required. |
400 | PLATFORM_NAME_TAKEN | name | Name has already been taken. |
400 | PLATFORM_NAME_TOO_LONG | name | Name cannot be more than 50 characters. |
400 | PLATFORM_SHORT_NAME_TAKEN | short_name | Short name has already been taken. |
400 | PLATFORM_SHORT_TOO_LONG | short_name | Short name cannot be more than 10 characters. |
400 | PLATFORM_SPHERE_BLANK | sphere | Sphere is required. |
400 | PLATFORM_SPHERE_INCLUSION | sphere | Sphere must be an accepted value. |
400 | PLATFORM_KIND_BLANK | kind | Kind is required. |
400 | PLATFORM_KIND_INCLUSION | kind | Kind must be an accepted value. |
400 | PLATFORM_HOLDER_ID_BLANK | holder_id | Holder is required. |
400 | PLATFORM_HOLDER_ID_INVALID | holder_id | Holder ID must be a valid company ID. |
400 | PLATFORM_PARENT_ID_INVALID | parent_id | Parent ID must be a valid platform ID. |
