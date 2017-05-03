## <a name="comany_names_create"></a>Create a new company name

> Request body | `POST /articles/companies/nintendo-co-ltd/names`

```JSON
{
  "data": {
    "type": "company_names",
    "attributes": {
      "name": "New Name",
      "kind": "name",
      "writing_system": "Latin",
      "year_adopted": "2010",
      "dropped": "",
      "year_dropped": "2017"
    },
    "relationships": {
      "place": {
        "data": {
          "id": "17",
          "type": "places"
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
    "id": "61",
    "type": "company_names",
    "attributes": {
      "name": "New Name",
      "kind": "name",
      "writing_system": "Latin",
      "year_adopted": 2010,
      "dropped": true,
      "year_dropped": 2017
    },
    "relationships": {
      "company": {
        "data": {
          "id": "1",
          "type": "companies"
        },
        "links": {
          "related": "http://localhost:3000/articles/companies/nintendo-co-ltd"
        }
      },
      "place": {
        "data": {
          "id": "17",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/bangladesh"
        }
      }
    }
  },
  "included": [
    {
      "id": "1",
      "type": "companies",
      "attributes": {
        "display_title": "Nintendo Co., Ltd."
      },
      "links": {
        "self": "http://localhost:3000/articles/companies/nintendo-co-ltd"
      }
    },
    {
      "id": "17",
      "type": "places",
      "attributes": {
        "name": "Bangladesh",
        "formatted": "Bangladesh"
      },
      "links": {
        "self": "http://localhost:3000/places/bangladesh"
      }
    }
  ],
  "meta": {
    "keywords": "new name, nintendo co., ltd., bangladesh, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "New Name is an alternate name or title for Nintendo Co., Ltd.. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-05-03T10:05:55.948Z",
    "updated_at": "2017-05-03T10:05:55.948Z"
  }
}
```

Create a new name record for a given company. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/companies/{company-slug}/names`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | 1-250 characters.
kind | string | Y | The name classification. Must be 'name', 'styled' or 'alias'.
writing_system | string | Y | Must be an accepted value.
year_adopted | integer | | Between 1800 and the present year.
dropped | boolean | | True if the name has been dropped. Auto-sets true if `year_dropped` present.
year_dropped | integer | | Between 1800 and the present year.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
place | belongs_to | | places | Can be a country or region.

### Success HTTP response code

`201 Created`
