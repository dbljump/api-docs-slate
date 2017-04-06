## <a name="regions_create"></a>Create a new region record

> Request body

```JSON
{
  "data": {
    "type": "places",
    "attributes": {
      "name": "New Region",
      "short_name": "NR"
      "also_known_as": ["That New Region", "The Newest"],
      "latitude": "5.0",
      "longitude": "-35.00"
    }
  }
}
```

> HTTP 201 response body

```JSON
```

Create a new region record. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /places/regions`

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

`201 Created`
