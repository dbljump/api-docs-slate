## <a name="regions_update"></a>Update a region record

> Request body

```JSON
{
  "data": {
    "type": "places",
    "id": "europe",
    "attributes": {
      "name": "Updated Region",
      "also_known_as": ["Edited Region", "Changed Region"],
      "latitude": "7.7",
      "longitude": "-65.4"
    }
  }
}
```

> HTTP 200 response body

```JSON
```

Update an existing region record. The user must be an admin.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /places/regions/{slug}` (replace `{slug}` with region record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | Unique. 2-50 chars. English-language common name, e.g. 'North America'.
short_name | string | | Unique. 2-20 chars. Common short name, e.g. 'NA'.
also_known_as | array | | Members must be 2-50 char strings. E.g. `['Norteamérica']`.
latitude | number/float | | Between -90 and 90.
longitude | number/float | | Between -180 and 180.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | ----------
countries | has_many |  | places (countries) | The [countries](#countries_intro) that belong to this region.

### Success HTTP response code

`200 OK`
