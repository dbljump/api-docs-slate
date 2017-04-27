## <a name="companies_errors"></a>Errors

Errors specific to creating and updating company articles.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | COMPANY_DISPLAY_TITLE_BLANK | display_title | Display title is required.
400 | COMPANY_DISPLAY_TITLE_TOO_LONG | display_title | Display title cannot be more than 250 characters.
400 | COMPANY_DESCRIPTION_TOO_LONG | description | Description cannot be more than 800 characters.
400 | COMPANY_FOUNDED_DATE_INCLUSION | founded_date | Founded date must be a past date not before 1800.
400 | COMPANY_FOUNDED_YEAR_INCLUSION | founded_year | Founded year must be a past year not before 1800.
400 | COMPANY_CLOSED_DATE_INCLUSION | closed_date | Closed date must be a past date not before 1800.
400 | COMPANY_CLOSED_DATE_INVALID | closed_date | Closed date must not be eariler than founded date.
400 | COMPANY_CLOSED_YEAR_INCLUSION | closed_year | Closed year must be a past year not before 1800.
400 | COMPANY_CLOSED_YEAR_INVALID | closed_year | Closed year must not be eariler than founded year.
