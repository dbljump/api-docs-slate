# Article data

Aliases, notes, credits, and company kinships use independent, non-nested
endpoints. Their IDs are numeric. All reads are public; create, update, and
delete operations require an editor unless stated otherwise.

## Aliases

Resource | Path | JSON:API type
-------- | ---- | -------------
Game alias | `/game-aliases` | `gameAlias`
Company alias | `/company-aliases` | `companyAlias`
Person alias | `/person-aliases` | `personAlias`

Each supports `GET` collection, `GET /{id}`, `POST`, `PATCH /{id}`, and
`DELETE /{id}`.

Common writable fields are `displayText`, `kind`, and `writingSystem`.
`writingSystem` must be one of `Arab`, `Hang`, `Hans`, `Hant`, `Cyrl`, `Grek`,
`Hebr`, `Jpan`, `Latn`, or `Thai`.

Alias | Extra fields | Allowed `kind`
----- | ------------ | --------------
Game | `gameVersions` relationship | `official`, `working`, `translated`, `AKA`
Company | `yearAdopted`, `dropped`, `yearDropped` | `official`, `styled`, `AKA`
Person | `givenNames`, `familyName`, `yearAdopted`, `dropped`, `yearDropped` | `official`, `full`, `AKA`

All aliases require an `article` relationship and may have `places`.

Queryable fields are `id`, `articleId`, `displayText`, `familyName`,
`givenNames`, `kind`, `writingSystem`, `yearAdopted`, `yearDropped`, `dropped`,
`createdAt`, and `updatedAt`.

## Notes

Resource | Path | JSON:API type
-------- | ---- | -------------
Game note | `/game-notes` | `gameNote`
Company note | `/company-notes` | `companyNote`
Person note | `/person-notes` | `personNote`

Each supports the full CRUD set.

Writable fields are `category`, `heading`, `body`, `spoiler`, and
`displayOrder`. Notes require an `article` relationship. Game notes can also
relate to `gameVersions`. Notes may be linked to `extResources`.

The body is Markdown, 5–5000 characters, and is returned both as `body` and
sanitized `bodyHtml`. External links are rejected in note Markdown; cite an
external resource through `extResources` instead. `heading` is at most 40
characters. If omitted during creation, `displayOrder` is appended
automatically within its article and category.

Note type | Allowed categories
--------- | ------------------
Game | `game`, `story`, `development`, `publishing`, `visuals`, `sound`, `addons`, `tech`, `profile`, `sales`, `impact`
Company | `history`, `organization`, `products`, `profile`, `sales`, `impact`
Person | `bio`, `education`, `career`, `views`, `profile`, `impact`

Queryable fields are `id`, `articleId`, `type`, `category`, `heading`,
`displayOrder`, `spoiler`, `extResources`, `createdById`, `createdAt`, and
`updatedAt`.

## Credits

Resource | Path | JSON:API type
-------- | ---- | -------------
Company credit | `/company-credits` | `companyCredit`
Person credit | `/person-credits` | `personCredit`

Both support the full CRUD set. Writable attributes are `role`, `category`,
and `leading`. Required relationships are `credited` and `game`; optional
many-valued relationships are `places` and `gameVersions`.

Company credit categories are `publishing`, `development`, `technology`,
`visuals`, `sound`, `language`, `special`, and `misc`.

Person credit categories are `creative`, `development`, `technology`,
`visuals`, `sound`, `language`, `special`, and `misc`.

Queryable fields are `id`, `creditedId`, `gameId`, `placeId`, `role`,
`category`, `leading`, `createdAt`, and `updatedAt`.

## Company kinships

`/company-kinships` uses type `companyKinship` and supports full CRUD.
Kinships connect a `parent` company and a different `child` company.

Writable fields are `kind`, `startYear`, and `endYear`. `kind` is `ownership`
or `division`; years start at 1800 and the end cannot precede the start.

Queryable fields are `id`, `parentId`, `childId`, `kind`, `startYear`,
`endYear`, `createdAt`, and `updatedAt`.
