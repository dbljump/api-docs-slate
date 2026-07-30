# Media

## Images

`/images` replaces the old `/media/images` path. Its JSON:API type is `image`.

Reads are public. Editors can create and update images. Admins can delete any
image; an editor can delete an image they uploaded.

### Writable attributes

Attribute | Description
--------- | -----------
`base64Image` | Required on create; a `data:image/...;base64,...` string. It cannot be changed later.
`kind` | Required: `artwork`, `boxart`, `doc`, `logo`, `photo`, `poster`, or `screen`.
`title` | Required; maximum 100 characters.
`description` | Optional; maximum 500 characters.
`year`, `date` | Image creation date, from 1800 through the present.
`usageType` | `free`, `fair`, or `licensed`.
`attributedName`, `attributedUrl` | Credit for the image creator or owner.
`sourceUrl` | Original source.

Writable relationships are `mediaLicense`, `place`, `articles`, `games`,
`companies`, and `people`.

Responses include `original`, `thumb`, `height`, `width`, `size`, `slug`,
`uploadedBy`, and `lastUpdatedBy`. `base64Image` is always returned as `null`.

Queryable fields are `id`, `kind`, `title`, `year`, `date`, `sortDate`,
`usageType`, `width`, `height`, `size`, `placeId`, `mediaLicenseId`,
`uploadedById`, `slug`, `createdAt`, and `updatedAt`. Use
`filter[articleIdEq]` to find images linked to an article.

## External resources

`/ext-resources` is used for citations and other material outside Dbljump.
The JSON:API type is `extResource`.

Reads are public. Editors can create and update; only admins can delete.

Writable attributes are `kind`, `title`, `authorNames`, `volumeTitle`, `doi`,
`publisher`, `year`, `date`, `sortDate`, `urlOriginal`, `urlArchived`,
`pageNumbersBegin`, and `pageNumbersEnd`. A `notes` relationship can link the
source to notes.

`kind` must be `book`, `print_article`, `twitter`, `web_article`, `webpage`,
`website`, or `youtube`. `urlOriginal` is required for every kind except
`book` and `print_article`. Page numbers are integers from 1–10000; supplying
only the beginning creates a one-page range.

The response also exposes `lastAccessedAt`, `approvedAt`, and `flaggedAt`,
which are currently response-only, plus `createdBy`.

Queryable fields are `id`, `kind`, `title`, `year`, `date`, `sortDate`,
`urlOriginal`, `urlArchived`, `volumeTitle`, `doi`, `publisher`,
`lastAccessedAt`, `approvedAt`, `flaggedAt`, `createdById`, `createdAt`, and
`updatedAt`.

## Media licenses

`/media-licenses` replaces `/media/licenses` and uses type `mediaLicense`.
Reads are public; only admins can create, update, or delete.

Writable attributes are `name` (required, unique, maximum 100 characters),
`shortName` (required, unique, maximum 15 characters), and `url` (required,
unique, maximum 250 characters). Responses include image totals in metadata.
