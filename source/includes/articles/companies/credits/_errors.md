## <a name="company_credits_errors"></a>Errors

Errors specific to creating and updating company credits.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | COMPANY_CREDIT_CREDITED_ID_BLANK | data/relationships/credited/data/id | Credited is required.
400 | COMPANY_CREDIT_GAME_ID_BLANK | data/relationships/game/data/id | Game is required.
400 | COMPANY_CREDIT_VERSION_ID_INVALID | data/relationships/version/data/id | Version ID must be a version of credit game.
400 | COMPANY_CREDIT_PLACE_ID_INVALID | data/relationships/place/data/id | Place ID must be a valid country or region ID.
400 | COMPANY_CREDIT_ROLE_BLANK | role | Role is required.
400 | COMPANY_CREDIT_ROLE_TOO_LONG | role | Role cannot be more than 100 characters.
400 | COMPANY_CREDIT_CATEGORY_BLANK | category | Category is required.
400 | COMPANY_CREDIT_CATEGORY_INCLUSION | category | Category must be an accepted value.
