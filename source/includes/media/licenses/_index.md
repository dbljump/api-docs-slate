## Get all media licenses

> Response body | `HTTP 200`

```JSON
# GET /media/licenses

{
    "data": [
        {
            "type": "media_licenses",
            "id": "cc_by_2_0",
            "attributes": {
                "name": "Creative Commons Attribution 2.0",
                "url": "https://creativecommons.org/licenses/by/2.0"
            }
        },
        {
            "type": "media_licenses",
            "id": "cc_by_2_5",
            "attributes": {
                "name": "Creative Commons Attribution 2.5",
                "url": "https://creativecommons.org/licenses/by/2.5/"
            }
        },
        {
            "type": "media_licenses",
            "id": "cc_by_sa_2_0",
            "attributes": {
                "name": "Creative Commons Attribution-ShareAlike 2.0",
                "url": "https://creativecommons.org/licenses/by-sa/2.0"
            }
        }
    ],
    "links": {
        "self": "http://localhost:3000/media/licenses"
    },
    "meta": {
        "total_items": 3
    }
}
```

Retrieve all media licenses. Useful for populating form select boxes.

* User authentication: not required

### HTTP request

`GET /media/licenses`

### URL query parameters

Not supported.

### Success HTTP response code

`200 OK`
