## Errors

Errors specific to creating and updating subdivision records.

<aside class="notice"><code>parent_id</code> refers to <code>country_id</code> in these errors.</aside>

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | PLACE_SUBDIVISION_PARENT_ID_BLANK | parent_id | Country ID is required.
400 | PLACE_SUBDIVISION_COUNTRY_ID_INVALID | country_id | Country ID must be a valid country record.
400 | PLACE_SUBDIVISION_NAME_BLANK | name | Name is required.
400 | PLACE_SUBDIVISION_NAME_TAKEN | name | There's already a subdivision with that name and parent country.
400 | PLACE_SUBDIVISION_NAME_TOO_SHORT | name | Name must be at least 2 characters.
400 | PLACE_SUBDIVISION_NAME_TOO_LONG | name | Name cannot be more than 50 characters.
400 | PLACE_SUBDIVISION_ALSO_KNOWN_AS_TOO_SHORT | also_known_as | Also-known-as tags must be at least 2 characters.
400 | PLACE_SUBDIVISION_ALSO_KNOWN_AS_TOO_LONG | also_known_as | Also-known-as tags cannot be more than 50 characters.
400 | PLACE_SUBDIVISION_LATITUDE_GREATER_THAN_OR_EQUAL_TO | latitude | Latitude must be between -90 and 90.
400 | PLACE_SUBDIVISION_LATITUDE_LESS_THAN_OR_EQUAL_TO | latitude | Latitude must be between -90 and 90.
400 | PLACE_SUBDIVISION_LONGITUDE_GREATER_THAN_OR_EQUAL_TO | longitude | Longitude must be between -180 and 180.
400 | PLACE_SUBDIVISION_LONGITUDE_LESS_THAN_OR_EQUAL_TO | longitude | Longitude must be between -180 and 180.
