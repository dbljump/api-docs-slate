## Errors

Errors specific to creating and updating country records.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | PLACE_COUNTRY_NAME_BLANK | name | Name is required.
400 | PLACE_COUNTRY_NAME_TAKEN | name | There's already a country with that name.
400 | PLACE_COUNTRY_NAME_TOO_SHORT | name | Name must be at least 2 characters.
400 | PLACE_COUNTRY_NAME_TOO_LONG | name | Name cannot be more than 50 characters.
400 | PLACE_COUNTRY_SHORT_NAME_TAKEN | short_name | There's already a country with that short name.
400 | PLACE_COUNTRY_SHORT_NAME_TOO_SHORT | short_name | Short name must be at least 2 characters.
400 | PLACE_COUNTRY_SHORT_NAME_TOO_LONG | short_name | Short name cannot be more than 20 characters.
400 | PLACE_COUNTRY_ALSO_KNOWN_AS_TOO_SHORT | also_known_as | Also-known-as tags must be at least 2 characters.
400 | PLACE_COUNTRY_ALSO_KNOWN_AS_TOO_LONG | also_known_as | Also-known-as tags cannot be more than 50 characters.
400 | PLACE_COUNTRY_LATITUDE_GREATER_THAN_OR_EQUAL_TO | latitude | Latitude must be between -90 and 90.
400 | PLACE_COUNTRY_LATITUDE_LESS_THAN_OR_EQUAL_TO | latitude | Latitude must be between -90 and 90.
400 | PLACE_COUNTRY_LONGITUDE_GREATER_THAN_OR_EQUAL_TO | longitude | Longitude must be between -180 and 180.
400 | PLACE_COUNTRY_LONGITUDE_LESS_THAN_OR_EQUAL_TO | longitude | Longitude must be between -180 and 180.
400 | PLACE_COUNTRY_ISO_CODE_BLANK | iso_code | ISO code is required.
400 | PLACE_COUNTRY_ISO_CODE_TAKEN | iso_code | There's already a country with that ISO code.
400 | PLACE_COUNTRY_ISO_CODE_TOO_SHORT | iso_code | ISO code must be at least 2 characters.
400 | PLACE_COUNTRY_ISO_CODE_TOO_LONG | iso_code | ISO code cannot be more than 2 characters.
400 | PLACE_COUNTRY_NATIONALITY_TOO_SHORT | nationality | Nationality must be at least 2 characters.
400 | PLACE_COUNTRY_NATIONALITY_TOO_LONG | nationality | Nationality cannot be more than 30 characters.
400 | PLACE_COUNTRY_CURRENCY_TOO_SHORT | currency | Currency must be at least 3 characters.
400 | PLACE_COUNTRY_CURRENCY_TOO_LONG | currency | Currency cannot be more than 3 characters.
