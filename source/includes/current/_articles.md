# Articles

Articles provide a combined read-only collection of games, companies, and
people.

Method | Path | Description
------ | ---- | -----------
GET | `/articles` | List all article types together.

Use the dedicated `/games`, `/companies`, and `/people` endpoints to fetch or
modify a single typed article.

## Attributes

Attribute | Description
--------- | -----------
`slug` | URL-friendly identifier generated from the display title.
`displayTitle` | Public title.
`description` | Summary of up to 800 characters.
`originDate` | Exact date of origin, when known.
`originYear` | Origin year; derived from `originDate` when a date is supplied.
`ended` | Whether the company or person's activity has ended.
`thumbnail` | Thumbnail URL derived from the primary image.

## Relationships

`images`, `primaryImage`, `headerImage`, `createdBy`, and `lastUpdatedBy`.

## Queryable fields

`id`, `type`, `displayTitle`, `sortTitle`, `slug`, `kind`, `originDate`,
`originSortDate`, `originYear`, `ended`, `status`, `createdById`,
`primaryImageId`, `headerImageId`, `createdAt`, and `updatedAt`.

> Find a single article by slug through the collection

```JSON
GET https://www.dbljump.com/articles?filter[slugEq]=pong
```
