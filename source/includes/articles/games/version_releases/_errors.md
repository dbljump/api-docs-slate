## <a name="version_releases_errors"></a>Errors

Errors specific to creating and updating game version releaes.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | VERSION_RELEASE_PLACE_ID_BLANK | data/relationships/place/data/id | Place is required.
400 | VERSION_RELEASE_PLACE_ID_TAKEN | data/relationships/place/data/id | There's already a release of this version for that place.
400 | VERSION_RELEASE_PLACE_ID_INVALID | data/relationships/place/data/id | Status is required.
400 | VERSION_RELEASE_DATE_INCLUSION | date | Date must be after 1799 and not more than 3 years in the future.
400 | VERSION_RELEASE_YEAR_INCLUSION | year | Year must be after 1799 and not more than 3 years in the future.
