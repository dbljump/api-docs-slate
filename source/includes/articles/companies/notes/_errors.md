## <a name="company_notes_errors"></a>Errors

Errors specific to creating and updating company notes.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | COMPANY_NOTE_CATEGORY_BLANK | category | Category is required.
400 | COMPANY_NOTE_CATEGORY_INCLUSION | category | Category must be an accepted value.
400 | COMPANY_NOTE_BODY_BLANK | body | Body is required.
400 | COMPANY_NOTE_BODY_TOO_SHORT | body | Body cannot be less than 5 characters.
400 | COMPANY_NOTE_BODY_TOO_LONG | body | Body cannot be more than 8000 characters.
400 | COMPANY_NOTE_CITE_URL_TOO_SHORT | cite_url | Cite URL cannot be less than 5 characters.
400 | COMPANY_NOTE_CITE_URL_TOO_LONG | cite_url | Cite URL cannot be more than 250 characters.
400 | COMPANY_NOTE_CITE_TITLE_TOO_LONG | cite_title | Cite title cannot be more than 250 characters.
400 | COMPANY_NOTE_CITE_WEBSITE_TOO_LONG | cite_website | Cite website cannot be more than 100 characters.
