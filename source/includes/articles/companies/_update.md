## <a name="companies_update"></a>Update a company

> Request body | `PATCH /articles/companies/microsoft-corporation`

```JSON
{
  "data": {
    "type": "companies",
    "id": "microsoft-corporation",
    "attributes": {
      "display_title": "Changed Name",
      "description": "Updated description for an updated article.",
      "founded_date": "1940-09-12",
      "founded_year": "",
      "dead": "",
      "closed_date": "2013-04-05",
      "closed_year": ""
    },
    "relationships": {
      "primary_image": {
        "data": {
          "id": "1",
          "type": "images"
        }
      },
      "founded_place": {
        "data": {
          "id": "25",
          "type": "places"
        }
      },
      "hq_place": {
        "data": {
          "id": "2933",
          "type": "places"
        }
      }
    }
  }
}
```

> Response body | `HTTP 200`

```JSON
{
  "data": {
    "id": "4",
    "type": "companies",
    "attributes": {
      "display_title": "Changed Name",
      "description": "Updated description for an updated article.",
      "founded_date": "1940-09-12",
      "founded_year": 1940,
      "closed": true,
      "closed_date": "2013-04-05",
      "closed_year": 2013,
      "slug": "changed-name-3b1258ec-cc74-41f3-966c-c075bb634a16"
    },
    "relationships": {
      "founded_place": {
        "data": {
          "id": "25",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/bolivia"
        }
      },
      "hq_place": {
        "data": {
          "id": "2933",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/sonobe-kyoto-prefecture-japan"
        }
      },
      "created_by": {
        "data": {
          "id": "1",
          "type": "users"
        },
        "links": {
          "related": "http://localhost:3000/users/1"
        }
      }
    },
    "links": {
      "self": "http://localhost:3000/articles/companies/changed-name-3b1258ec-cc74-41f3-966c-c075bb634a16"
    }
  },
  "included": [
    {
      "id": "25",
      "type": "places",
      "attributes": {
        "name": "Bolivia",
        "formatted": "Bolivia"
      },
      "links": {
        "self": "http://localhost:3000/places/bolivia"
      }
    },
    {
      "id": "2933",
      "type": "places",
      "attributes": {
        "name": "Sonobe",
        "formatted": "Sonobe, Kyoto Prefecture, Japan"
      },
      "links": {
        "self": "http://localhost:3000/places/sonobe-kyoto-prefecture-japan"
      }
    },
    {
      "id": "1",
      "type": "users",
      "attributes": {
        "username": "tikithekiwi",
        "role": "admin",
        "given_names": "Tiki",
        "family_name": "the Kiwi",
        "avatar": null
      },
      "links": {
        "self": "http://localhost:3000/users/1"
      }
    }
  ],
  "meta": {
    "keywords": "changed name, 1940, bolivia, sonobe, kyoto prefecture, japan, company, profile, biography, trivia, dbljump, video games, pc games, gaming",
    "description": "Find Changed Name's game credits, profile, images and facts at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:13.538Z",
    "updated_at": "2017-04-27T09:14:35.444Z"
  }
}
```

Update an existing company article. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/companies/{slug}` (replace `{slug}` with record slug)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | 1-250 characters.
description | text | | 1-800 characters.
founded_date | date | | Between 1st Jan 1800 and the present.
founded_year | integer | | Between 1800 and the present year.
closed | boolean | | True if the company has closed.
closed_date | date | | Between 1st Jan 1800 and the present.
closed_year | integer | | Between 1800 and the present year.

### Relationships

Check this section's code example to see how to update these relationships.

Name | Relationship | Req'd? | JSON:API type | Description
---- | ------------ | ------ | ------------- | -----------
primary_image | belongs_to | | images | The main article image, usually a company logo.
birth_place | belongs_to | | places | Can be a country, subdivision, or locality.
death_place | belongs_to | | places | Can be a country, subdivision, or locality.

### Success HTTP response code

`200 OK`
