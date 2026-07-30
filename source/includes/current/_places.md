# Places

`/places` contains geographical regions, countries, subdivisions, and
localities. The JSON:API type is `place`.

Method | Path | Authorization
------ | ---- | -------------
GET | `/places` | Public
GET | `/places/{id-or-slug}` | Public
POST | `/places` | Editor for localities; admin for all other kinds
PATCH | `/places/{id-or-slug}` | Admin, or the editor who created the locality
DELETE | `/places/{id-or-slug}` | Admin, or the editor who created the locality

## Writable fields

`kind` is required on create and selects the underlying place type. It must be
`region`, `country`, `subdivision`, or `locality`; it cannot be changed later.

Other writable attributes are `slug`, `name`, `latitude`, `longitude`, and
`isoCode`. Writable relationships are `parent`, `regions`, and `children`.

Responses also include `shortName`, `formatted`, `createdBy`, and
`lastUpdatedBy`. The retired nested `/places/{slug}/children` and
`/places/{slug}/regions` routes have been replaced by these relationships and
collection filters.

Queryable fields are `id`, `name`, `formatted`, `type`, `kind`, `isoCode`,
`slug`, `latitude`, `longitude`, `parentId`, `createdById`, `createdAt`, and
`updatedAt`.
