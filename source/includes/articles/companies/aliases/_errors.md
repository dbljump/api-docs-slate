## Errors

Errors specific to creating and updating company aliases.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | COMPANY_ALIAS_DISPLAY_TEXT_BLANK | name | Name is required.
400 | COMPANY_ALIAS_DISPLAY_TEXT_TOO_LONG | name | Name cannot be more than 250 characters.
400 | COMPANY_ALIAS_DISPLAY_TEXT_TAKEN | name | Name must be unique to its parent company.
400 | COMPANY_ALIAS_KIND_BLANK | kind | Kind is required.
400 | COMPANY_ALIAS_KIND_INCLUSION | kind | Kind must be an accepted value.
400 | COMPANY_ALIAS_WRITING_SYSTEM_BLANK | writing_system | Writing system is required.
400 | COMPANY_ALIAS_WRITING_SYSTEM_INCLUSION | writing_system | Writing system must be an accepted value.
400 | COMPANY_ALIAS_YEAR_ADOPTED_INCLUSION | year_adopted | Year adopted must be a past year not before 1800.
400 | COMPANY_ALIAS_YEAR_DROPPED_INCLUSION | year_dropped | Year dropped must be a past year not before 1800.
400 | COMPANY_ALIAS_YEAR_DROPPED_INVALID | year_dropped | Year dropped must not be earlier than year adopted.
400 | COMPANY_ALIAS_PLACE_ID_INVALID | data/relationships/place/data/id | Place ID must be a valid country or region ID.
