## <a name="person_names_errors"></a>Errors

Errors specific to creating and updating person names.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | PERSON_NAME_GIVEN_NAMES_BLANK | name | Given names is required.
400 | PERSON_NAME_GIVEN_NAMES_TOO_LONG | name | Given names cannot be more than 50 characters.
400 | PERSON_NAME_FAMILY_NAME_BLANK | name | Family name is required.
400 | PERSON_NAME_FAMILY_NAME_TOO_LONG | name | Family name cannot be more than 50 characters.
400 | PERSON_NAME_DISPLAY_NAME_TAKEN | name | This person already has a name record with that given names and family name combination.
400 | PERSON_NAME_KIND_BLANK | kind | Kind is required.
400 | PERSON_NAME_KIND_INCLUSION | kind | Kind must be an accepted value.
400 | PERSON_NAME_WRITING_SYSTEM_BLANK | writing_system | Writing system is required.
400 | PERSON_NAME_WRITING_SYSTEM_INCLUSION | writing_system | Writing system must be an accepted value.
400 | PERSON_NAME_YEAR_ADOPTED_INCLUSION | year_adopted | Year adopted must be a past year not before 1800.
400 | PERSON_NAME_YEAR_DROPPED_INCLUSION | year_dropped | Year dropped must be a past year not before 1800.
400 | PERSON_NAME_YEAR_DROPPED_INVALID | year_dropped | Year dropped must not be earlier than year adopted.
400 | PERSON_NAME_PLACE_ID_INVALID | data/relationships/place/data/id | Place ID must be a valid country or region ID.
