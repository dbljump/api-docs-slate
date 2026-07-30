# Introduction

The Dbljump API stores and serves structured information about video games,
their releases, creators, platforms, places, images, and sources.

The API follows the [JSON:API specification](https://jsonapi.org/) for normal
resource endpoints. Authentication handoffs and the health endpoint use small,
purpose-specific JSON responses.

## Base URL

All paths in this reference are relative to:

`https://www.dbljump.com`

For example:

`GET https://www.dbljump.com/games`

Use HTTPS for all production requests.

## Resource types

JSON:API resource types are singular and camel-cased where necessary. Examples
include `game`, `gameVersion`, `companyAlias`, `mediaLicense`, and `user`.

## Roles

Role | Description
---- | -----------
member | Can authenticate and manage their own user account.
editor | Includes member access and can create or edit articles and most article data.
admin | Full access, including administrative catalog records and destructive operations.

Read endpoints are public unless a resource section says otherwise.
