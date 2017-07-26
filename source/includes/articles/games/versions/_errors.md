## <a name="game_versions_errors"></a>Errors

Errors specific to creating and updating game version.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | GAME_VERSION_PLATFORM_ID_BLANK | data/relationships/platform/data/id | Platform ID is required.
400 | GAME_VERSION_PLATFORM_ID_TAKEN | data/relationships/platform/data/id | There's already a version of this game for that platform.
400 | GAME_VERSION_STATUS_BLANK | status | Status is required.
400 | GAME_VERSION_STATUS_INCLUSION | status | Status must be 'extant', 'rumored', 'canceled' or 'unknown'.
400 | GAME_VERSION_TARGET_FPS_LESS_THAN_OR_EQUAL_TO | target_fps | Target FPS must be less than or equal to 1000.
400 | GAME_VERSION_RESOLUTION_W_LESS_THAN_OR_EQUAL_TO | resolution_w | Resolution width must be less than or equal to 10,000.
400 | GAME_VERSION_RESOLUTION_H_LESS_THAN_OR_EQUAL_TO | resolution_h | Resolution height must be less than or equal to 10,000.
