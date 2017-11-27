## Errors

Errors specific to creating and updating game aliases.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | GAME_ALIAS_DISPLAY_TEXT_BLANK | title | Display text is required.
400 | GAME_ALIAS_DISPLAY_TEXT_TOO_LONG | title | Display text cannot be more than 250 characters.
400 | GAME_ALIAS_DISPLAY_TEXT_TAKEN | title | Display text must be unique to its parent company.
400 | GAME_ALIAS_KIND_BLANK | kind | Kind is required.
400 | GAME_ALIAS_KIND_INCLUSION | kind | Kind must be an accepted value.
400 | GAME_ALIAS_WRITING_SYSTEM_BLANK | writing_system | Writing system is required.
400 | GAME_ALIAS_WRITING_SYSTEM_INCLUSION | writing_system | Writing system must be an accepted value.
400 | GAME_ALIAS_PLACE_ID_INVALID | data/relationships/place/data/id | Place ID must be a valid country or region ID.
400 | GAME_ALIAS_VERSION_ID_INVALID | data/relationships/version/data/id | Version ID must belong to the parent game.
