# Platforms and genres

## Platforms

Platforms represent hardware, operating systems, streaming services, and
other environments on which a game version runs.

`/platforms` uses type `platform` and supports full CRUD. Reads are public,
editors can create and update, and only admins can delete.

Writable fields are:

Attribute | Requirements
--------- | ------------
`name` | Required, unique, maximum 50 characters.
`shortName` | Optional, unique, maximum 18 characters.
`sphere` | `arcade`, `cloud`, `home`, `mobile`, `non-gaming`, or `portable`.
`kind` | `add-on`, `OS`, `streaming`, or `system`.

Every platform requires a `holder` company relationship. Responses also
include `games`, `createdBy`, and `lastUpdatedBy`.

Queryable fields are `id`, `name`, `shortName`, `sphere`, `kind`, `slug`,
`holderId`, `createdById`, `createdAt`, and `updatedAt`.

## Genres

`/genres` uses type `genre` and supports full CRUD. Reads are public; only
admins can create, update, or delete genres.

Writable fields are `name` and `shortName`. Responses also provide the
generated `slug` and relationships to `games`, `createdBy`, and
`lastUpdatedBy`.

Queryable fields are `id`, `name`, `shortName`, `slug`, `createdById`,
`createdAt`, and `updatedAt`.
