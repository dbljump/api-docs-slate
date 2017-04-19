## <a name="genres_errors"></a>Errors

Errors specific to creating and updating genre records.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
400 | GENRE_NAME_BLANK | name | Name is required.
400 | GENRE_NAME_TAKEN | name | Name has already been taken.
400 | GENRE_NAME_TOO_SHORT | name | Name must be at least 2 characters.
400 | GENRE_NAME_TOO_LONG | name | Name cannot be more than 50 characters.
400 | GENRE_SHORT_NAME_TAKEN | short_name | Short name has already been taken.
400 | GENRE_SHORT_NAME_TOO_SHORT | short_name | Short name must be at least 2 characters.
400 | GENRE_SHORT_NAME_TOO_LONG | short_name | Short name cannot be more than 10 characters.
400 | GENRE_ALSO_KNOWN_AS_TOO_SHORT | also_known_as | Also-known-as tags must be at least 2 characters.
400 | GENRE_ALSO_KNOWN_AS_TOO_LONG | also_known_as | Also-known-as tags cannot be more than 50 characters.
400 | GENRE_PARENT_ID_INVALID | relationships/parent/data/id | Parent must be an existing, top-level genre.
