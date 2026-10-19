# Single-record examples

These examples show the current response shape for representative resources.
Exact IDs, timestamps, URLs, relationship counts, and included resources
depend on the database and the query parameters.

## Game response

> `GET https://www.dbljump.com/games/pong`

```JSON
{
  "data": {
    "id": "45",
    "type": "game",
    "attributes": {
      "slug": "pong",
      "displayTitle": "Pong",
      "description": "Pong is an early table-tennis video game.",
      "originDate": "1972-11-29",
      "originYear": 1972,
      "ended": null,
      "thumbnail": "https://www.dbljump.com/uploads/images/87/th_pong.jpg"
    },
    "relationships": {
      "platforms": {
        "data": [
          { "id": "4", "type": "platform" }
        ]
      },
      "genres": {
        "data": [
          { "id": "2", "type": "genre" }
        ]
      },
      "versions": {
        "data": [
          { "id": "71", "type": "gameVersion" }
        ]
      },
      "aliases": {
        "data": []
      },
      "notes": {
        "data": []
      },
      "companyCredits": {
        "data": [
          { "id": "108", "type": "companyCredit" }
        ]
      },
      "personCredits": {
        "data": []
      },
      "images": {
        "data": [
          { "id": "87", "type": "image" }
        ]
      },
      "primaryImage": {
        "data": { "id": "87", "type": "image" }
      },
      "headerImage": {
        "data": null
      },
      "createdBy": {
        "data": { "id": "1", "type": "user" }
      },
      "lastUpdatedBy": {
        "data": { "id": "1", "type": "user" }
      }
    },
    "meta": {
      "status": "published",
      "articleType": "game",
      "keywords": "Pong, 1972",
      "createdAt": "2026-01-12T10:30:00.000Z",
      "updatedAt": "2026-07-20T14:15:00.000Z",
      "total": {
        "images": 1,
        "versions": 1,
        "notes": 0,
        "genres": 1,
        "companyCredits": 1,
        "personCredits": 0
      }
    }
  }
}
```

Relationship objects contain resource linkage. Add `include`, for example
`?include=genres,primaryImage`, to return the related records in the top-level
`included` array.

## Game-version response

> `GET https://www.dbljump.com/game-versions/71`

```JSON
{
  "data": {
    "id": "71",
    "type": "gameVersion",
    "attributes": {
      "status": "extant",
      "interfaces": [
        "traditional"
      ],
      "audioChannels": 1.0,
      "audioSystem": "mono",
      "videoFpsTarget": 60,
      "videoFpsUnlocked": false,
      "videoResW": 640,
      "videoResH": 480,
      "videoResUnlocked": false,
      "videoInterlaced": false,
      "videoAspectRatio": "1.333",
      "videoHdr": false,
      "videoStereoscopic": false,
      "videoDynamicScaling": false,
      "playLocal": true,
      "playersLocalMin": 2,
      "playersLocalMax": 2,
      "playLocalVs": true,
      "playLocalCoOp": false,
      "playLocalTeams": false,
      "playLan": false,
      "playersLanMin": null,
      "playersLanMax": null,
      "playLanVs": false,
      "playLanCoOp": false,
      "playLanTeams": false,
      "playOnline": false,
      "playersOnlineMin": null,
      "playersOnlineMax": null,
      "playOnlineVs": false,
      "playOnlineCoOp": false,
      "playOnlineTeams": false
    },
    "relationships": {
      "game": {
        "data": { "id": "45", "type": "game" }
      },
      "platform": {
        "data": { "id": "4", "type": "platform" }
      },
      "releases": {
        "data": [
          { "id": "83", "type": "gameVersionRelease" }
        ]
      },
      "notes": {
        "data": []
      }
    },
    "meta": {
      "createdAt": "2026-02-02T09:00:00.000Z",
      "updatedAt": "2026-05-18T16:42:00.000Z"
    }
  }
}
```

## Image response

> `GET https://www.dbljump.com/images/pong-arcade-screen`

```JSON
{
  "data": {
    "id": "87",
    "type": "image",
    "attributes": {
      "base64Image": null,
      "original": "https://www.dbljump.com/uploads/images/87/pong.jpg",
      "thumb": "https://www.dbljump.com/uploads/images/87/th_pong.jpg",
      "kind": "screen",
      "title": "Pong arcade screen",
      "description": "A gameplay screen from the arcade release.",
      "height": 1080,
      "width": 1920,
      "size": "lg",
      "year": 1972,
      "date": null,
      "usageType": "fair",
      "attributedName": "Atari",
      "attributedUrl": null,
      "sourceUrl": "https://example.org/pong",
      "slug": "pong-arcade-screen"
    },
    "relationships": {
      "mediaLicense": {
        "data": null
      },
      "place": {
        "data": { "id": "840", "type": "place" }
      },
      "articles": {
        "data": [
          { "id": "45", "type": "article" }
        ]
      },
      "uploadedBy": {
        "data": { "id": "1", "type": "user" }
      },
      "lastUpdatedBy": {
        "data": { "id": "1", "type": "user" }
      }
    },
    "meta": {
      "createdAt": "2026-03-10T12:00:00.000Z",
      "updatedAt": "2026-03-10T12:00:00.000Z",
      "total": {
        "articles": 1
      }
    }
  }
}
```

The `base64Image` input is never echoed back. Consumers should use `original`
or `thumb`.

## External-resource response

> `GET https://www.dbljump.com/ext-resources/204`

```JSON
{
  "data": {
    "id": "204",
    "type": "extResource",
    "attributes": {
      "kind": "web_article",
      "title": "The history of Pong",
      "authorNames": [
        {
          "family": "Example",
          "given": "Alex"
        }
      ],
      "volumeTitle": "Game History Journal",
      "doi": null,
      "isbn": null,
      "issn": null,
      "publisher": "Example Publishing",
      "year": 2024,
      "date": "2024-06-12",
      "sortDate": "2024-06-12",
      "urlOriginal": "https://example.org/history-of-pong",
      "urlArchived": "https://example.org/archive/history-of-pong",
      "lastAccessedAt": "2026-07-28T10:15:00.000Z",
      "approvedAt": "2026-07-29T08:00:00.000Z",
      "flaggedAt": null,
      "pageNumbersBegin": null,
      "pageNumbersEnd": null
    },
    "relationships": {
      "createdBy": {
        "data": { "id": "1", "type": "user" }
      },
      "notes": {
        "data": [
          { "id": "19", "type": "gameNote" }
        ]
      },
      "consumerJoins": {
        "data": [
          { "id": "73", "type": "extResourceJoin" }
        ]
      }
    },
    "meta": {
      "createdAt": "2026-07-28T10:15:00.000Z",
      "updatedAt": "2026-07-29T08:00:00.000Z"
    }
  }
}
```

## Create a source with an initial citation

> `POST https://www.dbljump.com/ext-resources?include=consumerJoins`

```JSON
{
  "data": {
    "type": "extResource",
    "attributes": {
      "kind": "book",
      "title": "Example book",
      "isbn": "9780429771385",
      "initialCitationLocation": { "type": "pages", "start": "24", "end": "26" }
    },
    "relationships": {
      "notes": {
        "data": [ { "type": "gameNote", "id": "19" } ]
      }
    }
  }
}
```

An editor receives 201 on success. The response's primary resource is the new
`extResource`; its `attributes` do not contain `initialCitationLocation` or
`location`. The requested
`included` array contains the new `extResourceJoin` with the persisted page
location. Both records are rolled back if creation fails.

## Cite an existing source

> `POST https://www.dbljump.com/ext-resource-joins`

```JSON
{
  "data": {
    "type": "extResourceJoin",
    "attributes": {
      "location": { "type": "timestamp", "start": 760, "end": 845 }
    },
    "relationships": {
      "extResource": { "data": { "type": "extResource", "id": "206" } },
      "consumer": { "data": { "type": "gameNote", "id": "19" } }
    }
  }
}
```

Here resource 206 is an existing video source. The request creates a citation
for 12:40–14:05 without changing the shared resource. Success returns 201 with
the new citation as the primary resource. Repeating the same note/source pair
returns 422 and preserves the existing citation.

## Citation response

> `GET https://www.dbljump.com/ext-resource-joins/75`

```JSON
{
  "data": {
    "id": "75",
    "type": "extResourceJoin",
    "attributes": {
      "location": { "type": "timestamp", "start": 760, "end": 845 }
    },
    "relationships": {
      "extResource": { "data": { "id": "206", "type": "extResource" } },
      "consumer": { "data": { "id": "19", "type": "gameNote" } }
    }
  }
}
```

Alternatively, request `GET /ext-resources/206?include=consumerJoins` or
`GET /game-notes/19?include=extResourceJoins` to read the citation through a
related resource. To include sources with a note's citations, request
`GET /game-notes/19?include=extResourceJoins.extResource`.

## Edit or clear a citation location

> `PATCH https://www.dbljump.com/ext-resource-joins/75`

```JSON
{
  "data": {
    "type": "extResourceJoin",
    "id": "75",
    "attributes": {
      "location": { "type": "timestamp", "start": 900, "end": 915 }
    }
  }
}
```

This changes citation 75 to 15:00–15:15, leaving other citations and the shared
source unchanged. Success returns 200 with the updated citation.

> Clear the location with the same PATCH endpoint

```JSON
{
  "data": {
    "type": "extResourceJoin",
    "id": "75",
    "attributes": { "location": null }
  }
}
```

Omitting `location` preserves its current value. Explicit null clears the
location and retains the citation. `DELETE /ext-resource-joins/75` instead
removes the citation and returns 204, preserving source 206.
