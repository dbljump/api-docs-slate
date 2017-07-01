## Get all of a company's parent kinships

> Response body | `HTTP 200`

```JSON
# GET /articles/companies/retro-studios-inc/parents

{
    "data": [
        {
            "id": "2",
            "type": "company_kinships",
            "attributes": {
                "kind": "division",
                "start_year": null,
                "end_year": null
            },
            "relationships": {
                "parent": {
                    "data": {
                        "id": "1",
                        "type": "companies"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/companies/nintendo-co-ltd"
                    }
                },
                "child": {
                    "data": {
                        "id": "22",
                        "type": "companies"
                    },
                    "links": {
                        "related": "http://localhost:3000/articles/companies/retro-studios-inc"
                    }
                }
            }
        }
    ],
    "links": {},
    "meta": {
        "total_items": 1
    }
}
```

Retrieve all of a given company's parent kinships. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/companies/{company-slug}/parents` (replace `{company-slug}` with company record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[company_kinships]=kind`
filter[{field}] | All records | Filter search by field, e.g. `?filter[kind]=division`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
