## <a name="company_kinships_show"></a>Get a single company kinship

> Response body | `HTTP 200`

```JSON
# GET /articles/company_kinships/5

{
    "data": {
        "id": "5",
        "type": "company_kinships",
        "attributes": {
            "kind": "ownership",
            "start_year": null,
            "end_year": null
        },
        "relationships": {
            "parent": {
                "data": {
                    "id": "4",
                    "type": "companies"
                },
                "links": {
                    "related": "http://localhost:3000/articles/companies/microsoft-corporation"
                }
            },
            "child": {
                "data": {
                    "id": "17",
                    "type": "companies"
                },
                "links": {
                    "related": "http://localhost:3000/articles/companies/mojang-ab"
                }
            }
        }
    },
    "included": [
        {
            "id": "4",
            "type": "companies",
            "attributes": {
                "display_title": "Microsoft Corporation"
            },
            "links": {
                "self": "http://localhost:3000/articles/companies/microsoft-corporation"
            }
        },
        {
            "id": "17",
            "type": "companies",
            "attributes": {
                "display_title": "Mojang AB"
            },
            "links": {
                "self": "http://localhost:3000/articles/companies/mojang-ab"
            }
        }
    ],
    "meta": {
        "keywords": "Microsoft Corporation, Mojang AB, ownership, company, ownership, parent, division, subsidiary, branch, dbljump, video games, pc games, gaming",
        "description": "",
        "created_at": "2017-07-01T11:26:52.623Z",
        "updated_at": "2017-07-01T11:26:52.623Z"
    }
}
```

Retrieve a single company kinship record. Company kinships are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/company_kinships/{id}` (replace `{id}` with record ID)

### Success HTTP response code

`200 OK`

### <a name="company_kinships_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
kind | string | Y | The kinship classification. Must be 'ownership' or 'division'.
start_year | integer |  | Year the kinship was formed. Must be between 1800 and present year.
end_year | integer | | Year the kinship was ended. Must be between 1800 and present year.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
parent | companies | belongs_to
child | companies | belongs_to

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
