## <a name="company_kinship_create"></a>Create a new company kinship

> Request body | `POST /articles/company_kinships`

```JSON
{
  "data": {
    "type": "company_kinships",
    "attributes": {
      "kind": "ownership",
      "start_year": "1997",
      "end_year": ""
    },
    "relationships": {
      "child": {
        "data": {
          "id": "11",
          "type": "companies"
        }
      },
      "parent": {
        "data": {
          "id": "7",
          "type": "companies"
        }
      }
    }
  }
}
```

> Response body | `HTTP 201`

```JSON
{
    "data": {
        "id": "7",
        "type": "company_kinships",
        "attributes": {
            "kind": "ownership",
            "start_year": 1997,
            "end_year": null
        },
        "relationships": {
            "parent": {
                "data": {
                    "id": "7",
                    "type": "companies"
                },
                "links": {
                    "related": "http://localhost:3000/articles/companies/electronic-arts-inc-ea"
                }
            },
            "child": {
                "data": {
                    "id": "11",
                    "type": "companies"
                },
                "links": {
                    "related": "http://localhost:3000/articles/companies/ea-maxis"
                }
            }
        }
    },
    "included": [
        {
            "id": "7",
            "type": "companies",
            "attributes": {
                "display_title": "Electronic Arts, Inc. (EA)"
            },
            "links": {
                "self": "http://localhost:3000/articles/companies/electronic-arts-inc-ea"
            }
        },
        {
            "id": "11",
            "type": "companies",
            "attributes": {
                "display_title": "EA Maxis"
            },
            "links": {
                "self": "http://localhost:3000/articles/companies/ea-maxis"
            }
        }
    ],
    "meta": {
        "keywords": "Electronic Arts, Inc. (EA), EA Maxis, ownership, company, ownership, parent, division, subsidiary, branch, dbljump, video games, pc games, gaming",
        "description": "",
        "created_at": "2017-07-01T12:05:57.502Z",
        "updated_at": "2017-07-01T12:05:57.502Z"
    }
}
```

Create a new company kinship record. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/companies/{company-slug}/children`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
kind | string | Y | The name classification. Must be 'name', 'styled' or 'alias'.
start_year | integer |  | Year the kinship was formed. Must be between 1800 and present year.
end_year | integer | | Year the kinship was ended. Must be between 1800 and present year.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
parent | belongs_to | Y | companies | The parent company.
child | belongs_to | Y | companies | The child company.

### Success HTTP response code

`201 Created`
