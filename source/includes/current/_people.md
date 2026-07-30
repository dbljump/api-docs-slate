# People

People describe individuals credited in the video game industry.

Method | Path | Authorization
------ | ---- | -------------
GET | `/people` | Public
GET | `/people/{id-or-slug}` | Public
POST | `/people` | Editor
PATCH | `/people/{id-or-slug}` | Editor
DELETE | `/people/{id-or-slug}` | Admin, or the editor who created an unpublished person

The JSON:API type is `person`.

## Writable attributes

Attribute | Description
--------- | -----------
`givenNames` | Required on create; maximum 50 characters.
`familyName` | Optional; maximum 50 characters.
`displayTitle` | Accepted; on create it is generated from the supplied names.
`description` | Optional biography summary; maximum 800 characters.
`gender` | Optional free text; maximum 25 characters.
`originDate`, `originYear` | Birth date or year.
`ended`, `endDate`, `endYear` | Whether and when the person's life ended.

## Writable relationships

`originPlace`, `latestPlace`, `primaryImage`, `headerImage`, and `images`.

Response relationships include `aliases`, `notes`, `credits`, the place and
image relationships, `createdBy`, and `lastUpdatedBy`.

People use the article queryable fields plus `gender`, `endDate`,
`endSortDate`, and `endYear`.
