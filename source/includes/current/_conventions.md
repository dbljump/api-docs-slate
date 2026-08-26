# Requests and responses

## Headers

> Typical authenticated request

```JSON
GET https://www.dbljump.com/games
Accept: application/vnd.api+json
Content-Type: application/vnd.api+json
Authorization: Bearer {token}
```

Send `Accept: application/vnd.api+json`. Send
`Content-Type: application/vnd.api+json` when the request has a JSON:API body.
The old custom `version` media-type parameter is no longer used.

Authenticated requests use `Authorization: Bearer {token}`. Do not send an
Authorization header for signed-out requests.

## JSON:API document shape

> Minimal create request

```JSON
{
  "data": {
    "type": "game",
    "attributes": {
      "displayTitle": "New Game",
      "description": "A short description."
    }
  }
}
```

> Relationship linkage

```JSON
{
  "relationships": {
    "holder": {
      "data": { "type": "company", "id": "12" }
    }
  }
}
```

Create requests use `POST`; successful responses return `201 Created`. Update
requests use `PATCH`, must include the resource `id`, and return `200 OK`.
Deletes return `204 No Content`.

For an update, `data.type` and `data.id` must identify the same resource as the
request URL. A mismatch returns `409 Conflict` with the error code
`RESOURCE_MISMATCH` before any attributes or relationships are changed.

Serialized attribute, relationship, filter, sort, and include names use
lower camel case. IDs are strings in JSON:API documents.

## Collections

All collection endpoints are paginated. The default page size is 30.

Query | Purpose | Example
----- | ------- | -------
`page[size]` | Records per page | `?page[size]=20`
`page[number]` | One-based page number | `?page[number]=2`
`sort` | Sort by one or more allowed fields; prefix descending fields with `-` | `?sort=displayTitle,-originYear`
`filter[{field}{predicate}]` | Filter using an allowed field and Ransack predicate | `?filter[slugEq]=pong`
`search` | Full-text search on supported collections | `?search=nintendo`
`include` | Include related resources | `?include=createdBy,primaryImage`
`fields[{type}]` | Sparse fieldset | `?fields[game]=displayTitle,slug`

Collection responses include pagination information under
`meta.pagination`, including `records`, `current`, `first`, `prev`, `next`,
`last`, and `pages` when applicable.

## Filtering

The most common predicate is `Eq`, meaning equality. Other Ransack predicates
such as `Cont`, `Gteq`, and `Lteq` can be used with fields listed as queryable
in this reference.

The API accepts camel-case query names and converts them internally. Special
relationship filters include:

* `GET /games?filter[genreIdEq]={id}`
* `GET /games?filter[platformIdEq]={id}`
* `GET /images?filter[articleIdEq]={id}`
* `GET /game-version-releases?filter[gameIdEq]={id}`

A collection query using `filter[slugEq]` returns `404 Not Found` rather than
an empty collection when no record matches.

## Search

`search` is supported for articles, games, companies, people, users,
platforms, genres, places, and images.

## Metadata

All normal resources include `createdAt` and `updatedAt` in `meta`. Article
metadata also includes `status`, `articleType`, and `keywords`. Several
resources add relationship totals under `meta.total`.
