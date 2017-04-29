## <a name="games_errors"></a>Errors

Errors specific to creating and updating game articles.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | GAME_DISPLAY_TITLE_BLANK | display_title | Display title is required.
400 | GAME_DISPLAY_TITLE_TOO_LONG | display_title | Display title cannot be more than 250 characters.
400 | GAME_DESCRIPTION_TOO_LONG | description | Description cannot be more than 800 characters.
400 | GAME_RELEASE_DATE_INCLUSION | release_date | Release date must be a past date not before 1800.
400 | GAME_RELEASE_YEAR_INCLUSION | release_year | Release year must be a past year not before 1800.
