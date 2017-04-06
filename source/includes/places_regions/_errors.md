## Errors

Errors specific to creating and updating region records.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | PLACE_REGION_NAME_BLANK | name | Name is required.
400 | PLACE_REGION_NAME_TAKEN | name | There's already a region with that name.
400 | PLACE_REGION_NAME_TOO_SHORT | name | Name must be at least 2 characters.
400 | PLACE_REGION_NAME_TOO_LONG | name | Name cannot be more than 50 characters.
400 | PLACE_REGION_SHORT_NAME_TAKEN | short_name | There's already a region with that short name.
400 | PLACE_REGION_SHORT_NAME_TOO_SHORT | short_name | Short name must be at least 2 characters.
400 | PLACE_REGION_SHORT_NAME_TOO_LONG | short_name | Short name cannot be more than 20 characters.
400 | PLACE_REGION_ALSO_KNOWN_AS_TOO_SHORT | also_known_as | Also-known-as tags must be at least 2 characters.
400 | PLACE_REGION_ALSO_KNOWN_AS_TOO_LONG | also_known_as | Also-known-as tags cannot be more than 50 characters.
400 | PLACE_REGION_LATITUDE_GREATER_THAN_OR_EQUAL_TO | latitude | Latitude must be between -90 and 90.
400 | PLACE_REGION_LATITUDE_LESS_THAN_OR_EQUAL_TO | latitude | Latitude must be between -90 and 90.
400 | PLACE_REGION_LONGITUDE_GREATER_THAN_OR_EQUAL_TO | longitude | Longitude must be between -180 and 180.
400 | PLACE_REGION_LONGITUDE_LESS_THAN_OR_EQUAL_TO | longitude | Longitude must be between -180 and 180.
