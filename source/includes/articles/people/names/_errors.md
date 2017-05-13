## <a name="company_names_errors"></a>Errors

Errors specific to creating and updating company names.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | COMPANY_NAME_NAME_BLANK | name | Name is required.
400 | COMPANY_NAME_NAME_TOO_LONG | name | Name cannot be more than 250 characters.
400 | COMPANY_NAME_NAME_TAKEN | name | Name must be unique to its parent company.
400 | COMPANY_NAME_KIND_BLANK | kind | Kind is required.
400 | COMPANY_NAME_KIND_INCLUSION | kind | Kind must be an accepted value.
400 | COMPANY_NAME_WRITING_SYSTEM_BLANK | writing_system | Writing system is required.
400 | COMPANY_NAME_WRITING_SYSTEM_INCLUSION | writing_system | Writing system must be an accepted value.
400 | COMPANY_NAME_YEAR_ADOPTED_INCLUSION | year_adopted | Year adopted must be a past year not before 1800.
400 | COMPANY_NAME_YEAR_DROPPED_INCLUSION | year_dropped | Year dropped must be a past year not before 1800.
400 | COMPANY_NAME_YEAR_DROPPED_INVALID | year_dropped | Year dropped must not be earlier than year adopted.
400 | COMPANY_NAME_PLACE_ID_INVALID | data/relationships/place/data/id | Place ID must be a valid country or region ID.
