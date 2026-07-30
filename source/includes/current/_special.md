# Special endpoints

## Reorder article notes

`PATCH /article-note-orders/{id}` atomically reorders every note in one article
category. It requires an editor and returns `204 No Content`.

The resource ID is `{article-type}-{article-id}-{category}`, for example
`game-45-development`. Article type is `game`, `company`, or `person`.

> Reorder all development notes for game 45

```JSON
PATCH https://www.dbljump.com/article-note-orders/game-45-development

{
  "data": {
    "type": "article_note_order",
    "id": "game-45-development",
    "attributes": {
      "category": "development"
    },
    "relationships": {
      "article": {
        "data": { "type": "game", "id": "45" }
      },
      "notes": {
        "data": [
          { "type": "game_note", "id": "19" },
          { "type": "game_note", "id": "12" }
        ]
      }
    }
  }
}
```

Unlike normal serialized resources, this endpoint validates its raw resource
identifiers and therefore requires the snake-case types shown above.

The request must contain every note in the category exactly once. IDs must be
unique and must all belong to the specified article and category. An invalid
set returns `422 INVALID_NOTE_ORDER`; a mismatched URL or resource identity
returns `409 RESOURCE_MISMATCH`.

## Health

`GET /health` is a lightweight service health check. A healthy application
returns `200 OK` with an empty body.
