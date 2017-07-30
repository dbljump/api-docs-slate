## <a name="game_versions_errors"></a>Errors

Errors specific to creating and updating game version.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | GAME_VERSION_PLATFORM_ID_BLANK | data/relationships/platform/data/id | Platform ID is required.
400 | GAME_VERSION_PLATFORM_ID_TAKEN | data/relationships/platform/data/id | There's already a version of this game for that platform.
400 | GAME_VERSION_STATUS_BLANK | status | Status is required.
400 | GAME_VERSION_STATUS_INCLUSION | status | Status must be 'extant', 'rumored', 'canceled' or 'unknown'.
400 | GAME_VERSION_FPS_TARGET_LESS_THAN_OR_EQUAL_TO | fps_target | Target FPS must be less than or equal to 1000.
400 | GAME_VERSION_RES_W_LESS_THAN_OR_EQUAL_TO | res_w | Resolution width must be less than or equal to 10,000.
400 | GAME_VERSION_RES_H_LESS_THAN_OR_EQUAL_TO | res_h | Resolution height must be less than or equal to 10,000.
