# Media licenses

Users should only upload privately-owned media items (such as images) to Dbljump if they are published with a license that gives us the legal right to use them (e.g. Creative Commons licenses).

This resource catalogues such licenses. Through the `media/images` endpoint, it also allows us to relate licenses to media items so we can show proper rights attributions.

The JSON:API type for this resource is `media_licenses`.

### Mutable attributes

#### `name` (string, required, unique)

The license name. 1-100 chars.

#### `short_name` (string, required, unique)

A short version of the name. 1-15 chars.

#### `url` (string, required, unique)

The URL of the official web page for the license. 1-250 chars.

### Immutable relationships

These relationships cannot be updated at this endpoint.

Name | JSON:API type | Relationship type
------------ | ---------- | -----------------
`images` | `images` | Has many
`created_by` | `users` | Belongs to
`updated_by` | `users` | Belongs to
