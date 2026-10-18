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

`/ext-resources` stores shared information about material outside Dbljump.
The JSON:API type is `extResource`. A resource serves as a source when cited;
each citation is a separate `extResourceJoin` connecting it to a note. The
citation owns its passage location, so different notes can cite different
pages or timestamps in the same source.

Method | Path | Purpose
------ | ---- | -------
GET | `/ext-resources` | List, filter, sort, and paginate resources.
GET | `/ext-resources/{id}` | Read a shared resource.
POST | `/ext-resources` | Create a resource, optionally linked to notes.
PATCH | `/ext-resources/{id}` | Update shared resource details.
DELETE | `/ext-resources/{id}` | Delete the shared resource and its citation joins.

Reads are public. Editors can create and update; only admins can delete.

Writable attributes are `kind`, `title`, `authorNames`, `volumeTitle`, `doi`, `isbn`, `issn`,
`publisher`, `year`, `date`, `sortDate`, `urlOriginal`, `urlArchived`,
`pageNumbersBegin`, and `pageNumbersEnd`. `title` and `kind` are required.
DOI, ISBN, and ISSN are separate optional strings; no checksum or identifier
format validation is currently enforced.

The to-many `notes` relationship links the source to notes. Each identifier
must use `gameNote`, `companyNote`, or `personNote`, with an ID belonging to
that declared type. Omitting `notes` on PATCH preserves the existing links;
supplying it replaces those links, and an empty `data` array clears them.
Use the citation routes below to edit or remove an individual citation.

`kind` must be `book`, `print_article`, `twitter`, `web_article`, `webpage`,
`website`, or `youtube`. `urlOriginal` is required for every kind except
`book` and `print_article`. Page numbers are integers from 1–10000; supplying
only the beginning creates a one-page range.

The shared `pageNumbersBegin` and `pageNumbersEnd` fields describe publication
pages. A cited passage uses the separate citation `location` described below.

### Creating a resource with a citation location

`POST /ext-resources` also accepts `attributes.location` as a creation-only
input. A non-null location requires exactly one note in `relationships.notes`.
The API saves the resource and that note's citation location in one transaction;
if either fails, neither record is created. A resource may be created without
notes when its location is omitted or null.

The input is stored on the citation join. It is never returned as an attribute
of the shared resource. Read `consumerJoins`, or request
`include=consumerJoins`, to retrieve the citation IDs and stored locations.
`PATCH /ext-resources/{id}` rejects `attributes.location`, including null;
update the individual join instead.

### Response and query fields

The response also exposes `lastAccessedAt`, `approvedAt`, and `flaggedAt`,
which are currently response-only, plus the `createdBy`, `notes`, and
`consumerJoins` relationships. A resource's `consumerJoins` may also contain
other consumer types; the citation routes below support note consumers only.

Queryable fields are `id`, `kind`, `title`, `year`, `date`, `sortDate`,
`urlOriginal`, `urlArchived`, `volumeTitle`, `doi`, `isbn`, `issn`, `publisher`,
`lastAccessedAt`, `approvedAt`, `flaggedAt`, `createdById`, `createdAt`, and
`updatedAt`.

Full-text `search` is not currently supported for external resources. Use the
listed filter fields and standard pagination. URL normalization is not
implemented; preserve meaningful query parameters in source URLs.

## Citations (external-resource joins)

`/ext-resource-joins` manages individual citations. Its JSON:API type is
`extResourceJoin`. Reads are public; editors can create, update, and remove
note citations. These joins share the external-resource policy, while deleting
a shared external resource still requires an admin.

Method | Path | Purpose
------ | ---- | -------
POST | `/ext-resource-joins` | Cite an existing resource from a note.
GET | `/ext-resource-joins/{id}` | Read a citation and its location.
PATCH | `/ext-resource-joins/{id}` | Change or clear a citation's location.
DELETE | `/ext-resource-joins/{id}` | Remove the citation, preserving its source and other citations.

There is no citation collection GET endpoint. Obtain citation IDs from a
resource's `consumerJoins` relationship or a note's `extResourceJoins`
relationship. Both support inclusion to retrieve the join records.

### Citation requests and responses

Creation requires two to-one relationships:

Relationship | Type | Meaning
------------ | ---- | -------
`extResource` | `extResource` | The existing shared source.
`consumer` | `gameNote`, `companyNote`, or `personNote` | The note citing it; the ID must belong to the declared type.

`location` is the only writable citation attribute and is optional. Responses
return `attributes.location` and both relationship identifiers. Creating a
second citation from the same note to the same source returns 422 with code
`taken` and pointer `/data/relationships/extResource`; it does not replace the
existing citation or location.

PATCH requires `data.type: "extResourceJoin"` and the citation's own `data.id`.
Omitting `location` preserves it; `location: null` clears it without removing
the citation. PATCH rejects non-empty `relationships`: the source and note
cannot be reassigned through this endpoint. Delete the citation and create a
new one to change either relationship.

### Citation locations

`location` is null or one JSON object. Its `type` selects the following fields;
unknown types and extra fields are rejected. All text values must be nonblank
strings and are plain text rather than HTML or Markdown.

Type | Example | Rules
---- | ------- | -----
`pages` | `{"type":"pages","start":"24","end":"26"}` | Required string `start`; optional string `end`. Labels such as `iv` or `S12` are allowed. When both labels contain only decimal digits, the end cannot precede the start; other labels are not ordered by the API.
`timestamp` | `{"type":"timestamp","start":760,"end":845}` | Required integer `start`; optional integer `end`. Both are nonnegative whole seconds, and the end cannot precede the start. This example denotes 12:40–14:05.
`chapter` | `{"type":"chapter","value":"3"}` | Required string `value`, containing a number or title.
`section` | `{"type":"section","value":"2.1"}` | Required string `value`, containing a number or title.
`other` | `{"type":"other","value":"Table 3"}` | Required string `value` describing the passage.

Omit `end` for a single page or timestamp; do not supply `end: null`.
Time strings such as `"12:40"` are not accepted: clients must convert them to
whole seconds. Setting the entire location to null is the way to clear it.

Malformed document structures return 400 with code `BAD_REQUEST`. Invalid
location objects return 422 with code `invalid` and pointer
`/data/attributes/location`. Unsupported note types return 422; an ID not
found within its declared note type returns 404. A mismatched primary type
on POST, or type/ID on PATCH, returns 409 with code `RESOURCE_MISMATCH`.

## Media licenses

`/media-licenses` replaces `/media/licenses` and uses type `mediaLicense`.
Reads are public; only admins can create, update, or delete.

Writable attributes are `name` (required, unique, maximum 100 characters),
`shortName` (required, unique, maximum 15 characters), and `url` (required,
unique, maximum 250 characters). Responses include image totals in metadata.
