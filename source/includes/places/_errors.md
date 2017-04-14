## Errors

Errors specific to creating and updating place records.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | PLACE_KIND_BLANK | kind | Kind is required.
400 | PLACE_KIND_INCLUSION | kind | Kind must be 'region', 'country', 'subdivision' or 'locality'.
400 | PLACE_KIND_PRESENT | kind | Kind cannot be changed.
400 | PLACE_NAME_BLANK | name | Name is required.
400 | PLACE_NAME_TAKEN | name | Name has already been taken.
400 | PLACE_NAME_TOO_SHORT | name | Name must be at least 2 characters.
400 | PLACE_NAME_TOO_LONG | name | Name cannot be more than 50 characters.
400 | PLACE_SHORT_NAME_TAKEN | short_name | Short name has already been taken.
400 | PLACE_SHORT_NAME_TOO_SHORT | short_name | Short name must be at least 2 characters.
400 | PLACE_SHORT_NAME_TOO_LONG | short_name | Short name cannot be more than 20 characters.
400 | PLACE_ALSO_KNOWN_AS_TOO_SHORT | also_known_as | Also-known-as tags must be at least 2 characters.
400 | PLACE_ALSO_KNOWN_AS_TOO_LONG | also_known_as | Also-known-as tags cannot be more than 50 characters.
400 | PLACE_LATITUDE_GREATER_THAN_OR_EQUAL_TO | latitude | Latitude must be between -90 and 90.
400 | PLACE_LATITUDE_LESS_THAN_OR_EQUAL_TO | latitude | Latitude must be between -90 and 90.
400 | PLACE_LONGITUDE_GREATER_THAN_OR_EQUAL_TO | longitude | Longitude must be between -180 and 180.
400 | PLACE_LONGITUDE_LESS_THAN_OR_EQUAL_TO | longitude | Longitude must be between -180 and 180.
400 | PLACE_ISO_CODE_BLANK | iso_code | ISO code is required for country records.
400 | PLACE_ISO_CODE_PRESENT | iso_code | ISO code is only used by country records.
400 | PLACE_ISO_CODE_TAKEN | iso_code | There's already a country with that ISO code.
400 | PLACE_ISO_CODE_TOO_SHORT | iso_code | ISO code must be 2 characters long.
400 | PLACE_ISO_CODE_TOO_LONG | iso_code | ISO code must be 2 characters long.
400 | PLACE_PARENT_BLANK | relationships/parent/data/id | Parent is required for subdivisions and localities.
400 | PLACE_PARENT_PRESENT | relationships/parent/data/id | Regions and countries cannot have a parent place.
400 | PLACE_PARENT_INVALID | relationships/parent/data/id | That parent place ID isn't valid.
400 | PLACE_CHILDREN_PRESENT | relationships/parent/data/id | Localities cannot cannot contain child places.
400 | PLACE_CHILDREN_INVALID | relationships/parent/data/id | At least one of the child place IDs isn't valid.
