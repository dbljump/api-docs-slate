## <a name="game_titles_errors"></a>Errors

Errors specific to creating and updating game titles.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | GAME_TITLE_TITLE_BLANK | title | Title is required.
400 | GAME_TITLE_TITLE_TOO_LONG | title | Title cannot be more than 250 characters.
400 | GAME_TITLE_TITLE_TAKEN | title | Title must be unique to its parent company.
400 | GAME_TITLE_KIND_BLANK | kind | Kind is required.
400 | GAME_TITLE_KIND_INCLUSION | kind | Kind must be an accepted value.
400 | GAME_TITLE_WRITING_SYSTEM_BLANK | writing_system | Writing system is required.
400 | GAME_TITLE_WRITING_SYSTEM_INCLUSION | writing_system | Writing system must be an accepted value.
400 | GAME_TITLE_PLACE_ID_INVALID | data/relationships/place/data/id | Place ID must be a valid country or region ID.
400 | GAME_TITLE_VERSION_ID_INVALID | data/relationships/version/data/id | Version ID must belong to the parent game.
