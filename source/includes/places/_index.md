## Get all places

> HTTP 200 response body

```JSON
{
  "data": [
    {
      "id": "1",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "afghanistan",
        "name": "Afghanistan",
        "short_name": null,
        "formatted": "Afghanistan"
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/afghanistan"
      }
    },
    {
      "id": "2",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "albania",
        "name": "Albania",
        "short_name": null,
        "formatted": "Albania"
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/albania"
      }
    },
    {
      "id": "3",
      "type": "places",
      "attributes": {
        "subtype": "countries",
        "slug": "algeria",
        "name": "Algeria",
        "short_name": null,
        "formatted": "Algeria"
      },
      "links": {
        "self": "http://api.dbljump.com/places/countries/algeria"
      }
    }
  ],
  "links": {
    "self": "http://api.dbljump.com/places?page%5Bnumber%5D=1&page%5Bsize%5D=3",
    "next": "http://api.dbljump.com/places?page%5Bnumber%5D=2&page%5Bsize%5D=3",
    "last": "http://api.dbljump.com/places?page%5Bnumber%5D=979&page%5Bsize%5D=3"
  },
  "meta": {
    "total_items": 2936
  }
}
```

Retrieve all places. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /places`

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
page[number] | 1 | Select the page number
page[size] | 30 | Select the number of images per page

### Success HTTP response code

`200 OK`
