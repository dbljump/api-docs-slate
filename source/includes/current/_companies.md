# Companies

Companies describe publishers, developers, technology firms, and other
organizations associated with games.

Method | Path | Authorization
------ | ---- | -------------
GET | `/companies` | Public
GET | `/companies/{id-or-slug}` | Public
POST | `/companies` | Editor
PATCH | `/companies/{id-or-slug}` | Editor
DELETE | `/companies/{id-or-slug}` | Admin, or the editor who created an unpublished company

The JSON:API type is `company`.

## Writable attributes

`displayTitle` (required, 1–250 characters), `description` (maximum 800
characters), `originDate`, `originYear`, `ended`, `endDate`, and `endYear`.

Dates and years begin at 1800. `endDate` and `endYear` describe when the
organization ceased operating.

## Writable relationships

`originPlace`, `latestPlace`, `primaryImage`, `headerImage`, and `images`.

## Response-only fields and relationships

`shortName` is derived from the newest active styled alias, falling back to
`displayTitle`.

Relationships include `aliases`, `notes`, `credits`, `parentKinships`,
`childKinships`, `platforms`, `originPlace`, `latestPlace`, the common article
image relationships, `createdBy`, and `lastUpdatedBy`.

Companies use the article queryable fields plus `endDate`, `endSortDate`, and
`endYear`.
