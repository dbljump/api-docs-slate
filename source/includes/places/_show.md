## <a name="places_show"></a>Get single place

> HTTP 200 response body

```JSON
{
  "data": {
    "id": "2894",
    "type": "places",
    "attributes": {
      "subtype": "localities",
      "slug": "austin-texas-united-states",
      "name": "Austin",
      "short_name": null,
      "formatted": "Austin, Texas, United States"
    },
    "links": {
      "self": "http://api.dbljump.com/places/localities/austin-texas-united-states"
    }
  },
  "meta": {
    "keywords": "austin, texas, united states, city, town, place, dbljump, video games, pc games, gaming",
    "description": "Find video game companies and games industry professionals from Austin, Texas, United States at Dbljump.",
    "created_at": "2017-03-30T12:40:05.924Z",
    "updated_at": "2017-03-30T12:40:05.924Z"
  }
}
```

Retrieve a single place record. Places are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places/{slug}` (replace `{slug}` with place record slug)

### Success HTTP response code

`200 OK`

### <a name="place_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
subtype | string | Y | The place subclass. Either 'countries', 'subdivisions', or 'localities'.
slug | string | Y | A record ID based on the formatted name, e.g. 'glasgow-scotland-united-kingdom'.
name | string | Y | The place name, e.g. 'Glasow' or 'Scotland' or 'United Kingdom'.
short_name | array | | A commonly-used short name, e.g. 'USA' or 'UK'.
formatted_name | string | Y | The full name including parent places, e.g. 'Glasgow, Scotland, United Kingdom'.
