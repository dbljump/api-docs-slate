## <a name="people_errors"></a>Errors

Errors specific to creating person articles.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | PERSON_GIVEN_NAMES_BLANK | given_names | 'Given names' is required when creating a person record.
400 | PERSON_GIVEN_NAMES_TOO_LONG | given_names | Given names cannot be more than 50 characters.
400 | PERSON_FAMILY_NAME_TOO_LONG | family_name | Family name cannot be more than 50 characters.

Errors specific to creating person articles.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | PERSON_DISPLAY_TITLE_BLANK | display_title | Display title is required.
400 | PERSON_DISPLAY_TITLE_TOO_LONG | display_title | Display title cannot be more than 250 characters.

Errors that apply to creating and updating person articles.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | PERSON_DESCRIPTION_TOO_LONG | description | Description cannot be more than 800 characters.
400 | PERSON_GENDER_INCLUSION | gender | Gender must be 'male', 'female', 'transman' or 'transwoman'.
400 | PERSON_ORIGIN_DATE_INCLUSION | origin_date | Birth date must be a past date not before 1800.
400 | PERSON_ORIGIN_YEAR_INCLUSION | origin_year | Birth year must be a past year not before 1800.
400 | PERSON_END_DATE_INCLUSION | end_date | Death date must be a past date not before 1800.
400 | PERSON_END_DATE_INVALID | end_date | Death date must not be eariler than birth date.
400 | PERSON_END_YEAR_INCLUSION | end_year | Death year must be a past year not before 1800.
400 | PERSON_END_YEAR_INVALID | end_year | Death year must not be eariler than birth year.
