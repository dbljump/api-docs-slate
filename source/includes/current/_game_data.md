# Game versions and releases

## Game versions

`/game-versions` uses JSON:API type `gameVersion` and supports:

Method | Path | Authorization
------ | ---- | -------------
GET | `/game-versions` | Public
GET | `/game-versions/{id}` | Public
POST | `/game-versions` | Editor
PATCH | `/game-versions/{id}` | Editor
DELETE | `/game-versions/{id}` | Editor

Every version requires one `game` and one `platform`. A game can have only one
version per platform.

### Writable attributes

Group | Attributes
----- | ----------
General | `status`, `interfaces`, `audioChannels`, `audioSystem`
Video | `videoFpsTarget`, `videoFpsUnlocked`, `videoResW`, `videoResH`, `videoResUnlocked`, `videoInterlaced`, `videoAspectRatio`, `videoHdr`, `videoStereoscopic`, `videoDynamicScaling`
Local play | `playLocal`, `playersLocalMin`, `playersLocalMax`, `playLocalVs`, `playLocalCoOp`, `playLocalTeams`
LAN play | `playLan`, `playersLanMin`, `playersLanMax`, `playLanVs`, `playLanCoOp`, `playLanTeams`
Online play | `playOnline`, `playersOnlineMin`, `playersOnlineMax`, `playOnlineVs`, `playOnlineCoOp`, `playOnlineTeams`

`status` is `extant`, `rumored`, `canceled`, or `unknown`. `interfaces` accepts
`traditional`, `touch`, `motion`, `vision`, `vr`, `ar`, `camera`, `trackball`,
`pressure`, `lightgun`, `vehicle`, `custom`, or `3d`.

Player counts are cleared when their corresponding `playLocal`, `playLan`, or
`playOnline` flag is false. Each maximum must be at least its minimum.

Response relationships are `game`, `platform`, `releases`, and `notes`.

Queryable fields are `id`, `gameId`, `platformId`, `status`,
`videoFpsTarget`, `videoFpsUnlocked`, `videoResW`, `videoResH`,
`videoResUnlocked`, `createdAt`, and `updatedAt`.

## Game version releases

`/game-version-releases` uses type `gameVersionRelease` and supports the full
CRUD set, with editor authorization for writes.

Writable fields are `date`, `year`, `physical`, and `digital`. Each release
requires a `version` relationship and at least one `places` relationship.
Dates and years may be up to three years in the future. A version cannot have
two releases with the same derived sort date.

Responses include `version`, `game`, `platform`, and `places`.

Queryable fields are `id`, `versionId`, `placeId`, `date`, `year`, `physical`,
`digital`, `sortDate`, `createdAt`, and `updatedAt`. Use
`filter[gameIdEq]` to return releases belonging to any version of a game.
