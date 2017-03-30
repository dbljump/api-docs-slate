## <a name="localities_errors"></a>Errors

Errors specific to creating and updating locality records.

<aside class="notice"><code>parent_id</code> refers to <code>subdivision_id</code> in these errors.</aside>

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | PLACE_LOCALITY_PARENT_ID_BLANK | parent_id | Subdivision ID is required.
400 | PLACE_LOCALITY_PARENT_ID_INVALID | parent_id | Subdivision ID must be a valid subdivision record.
400 | PLACE_LOCALITY_NAME_BLANK | name | Name is required.
400 | PLACE_LOCALITY_NAME_TAKEN | name | There's already a locality with that name and parent subdivision.
400 | PLACE_LOCALITY_NAME_TOO_SHORT | name | Name must be at least 2 characters.
400 | PLACE_LOCALITY_NAME_TOO_LONG | name | Name cannot be more than 50 characters.
400 | PLACE_LOCALITY_ALSO_KNOWN_AS_TOO_SHORT | also_known_as | Also-known-as tags must be at least 2 characters.
400 | PLACE_LOCALITY_ALSO_KNOWN_AS_TOO_LONG | also_known_as | Also-known-as tags cannot be more than 50 characters.
400 | PLACE_LOCALITY_LATITUDE_GREATER_THAN_OR_EQUAL_TO | latitude | Latitude must be between -90 and 90.
400 | PLACE_LOCALITY_LATITUDE_LESS_THAN_OR_EQUAL_TO | latitude | Latitude must be between -90 and 90.
400 | PLACE_LOCALITY_LONGITUDE_GREATER_THAN_OR_EQUAL_TO | longitude | Longitude must be between -180 and 180.
400 | PLACE_LOCALITY_LONGITUDE_LESS_THAN_OR_EQUAL_TO | longitude | Longitude must be between -180 and 180.
