# Games

Games are the central articles in the database. A game can have multiple
platform versions, releases, aliases, notes, images, genres, and credits.

Method | Path | Authorization
------ | ---- | -------------
GET | `/games` | Public
GET | `/games/{id-or-slug}` | Public
POST | `/games` | Editor
PATCH | `/games/{id-or-slug}` | Editor
DELETE | `/games/{id-or-slug}` | Admin, or the editor who created an unpublished game

The JSON:API type is `game`.

## Writable attributes

Attribute | Create | Update | Description
--------- | ------ | ------ | -----------
`displayTitle` | Yes | Yes | Required; 1–250 characters.
`description` | Yes | Yes | Optional; maximum 800 characters.
`originDate` | Yes | Yes | Date from 1800 onward.
`originYear` | Yes | Yes | Year from 1800 onward.

## Writable relationships

Updates additionally accept `genres`, `primaryImage`, `headerImage`, and
`images`. These relationships are intentionally not accepted during creation.

## Response relationships

`platforms`, `genres`, `versions`, `aliases`, `notes`, `companyCredits`,
`personCredits`, `images`, `primaryImage`, `headerImage`, `createdBy`, and
`lastUpdatedBy`.

## Querying games

Games use the article queryable fields. They also support `genreIdEq` and
`platformIdEq`; when both are supplied, only games matching both are returned.

> Filter by genre and platform

```JSON
GET https://www.dbljump.com/games?filter[genreIdEq]=3&filter[platformIdEq]=8
```

> Create a game

```JSON
POST https://www.dbljump.com/games

{
  "data": {
    "type": "game",
    "attributes": {
      "displayTitle": "New Game",
      "description": "A concise description of the game.",
      "originYear": 2026
    }
  }
}
```

New games begin with `draft` status. Status is returned in article metadata and
is not directly writable by this endpoint.
