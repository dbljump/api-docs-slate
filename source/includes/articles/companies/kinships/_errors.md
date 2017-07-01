## <a name="company_kinships_errors"></a>Errors

Errors specific to creating and updating company kinships.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | COMPANY_KINSHIP_KIND_BLANK | kind | Kind is required.
400 | COMPANY_KINSHIP_KIND_INCLUSION | kind | Kind must be an accepted value.
400 | COMPANY_KINSHIP_START_YEAR_INCLUSION | start_year | Start year must be a past year not before 1800.
400 | COMPANY_KINSHIP_END_YEAR_INCLUSION | end_year | End year must be a past year not before 1800.
400 | COMPANY_KINSHIP_END_YEAR_INVALID | end_year | End year must not be earlier than start year.
400 | COMPANY_KINSHIP_PARENT_ID_BLANK | data/relationships/parent/data/id | Parent is required.
400 | COMPANY_KINSHIP_CHILD_ID_BLANK | data/relationships/child/data/id | Child is required.
400 | COMPANY_KINSHIP_PARENT_ID_INCLUSION | data/relationships/parent/data/id | Parent ID must not be the same as child ID.
