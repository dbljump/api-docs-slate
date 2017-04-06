## <a name="regions_show"></a>Get single region

> HTTP 200 response body

```JSON
```

Retrieve a single region record. Regions are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/regions/{slug}` (replace `{slug}` with country record slug)

### Success HTTP response code

`200 OK`

### <a name="region_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
subtype | string | Y | The place subclass. Always 'regions'.
slug | string | Y | A record ID based on the formatted name, e.g. 'north-america'.
name | string | Y | English-language common name, e.g. 'North America'.
short_name | string | | A common short name, e.g. 'NA'.
formatted | string | Y | Has the same value as `name`.
also_known_as | array | | Other names the country is known by, e.g. `['Norteamérica']`.
latitude | number/float | | Global coordinate.
longitude | number/float | | Global coordinate.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
created_by | users | belongs_to
countries | places (countries) | has_many

### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
