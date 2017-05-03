## <a name="companies_show"></a>Get a single company

> Response body | `HTTP 200`

```JSON
# GET /articles/companies/nintendo-co-ltd

{
  "data": {
    "id": "1",
    "type": "companies",
    "attributes": {
      "display_title": "Nintendo Co., Ltd.",
      "description": "Nintendo is a Japanese video game hardware and software company founded in 1889.",
      "founded_date": null,
      "founded_year": 1889,
      "closed": null,
      "closed_date": null,
      "closed_year": null,
      "slug": "nintendo-co-ltd"
    },
    "relationships": {
      "founded_place": {
        "data": {
          "id": "2932",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
        }
      },
      "hq_place": {
        "data": null
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
      "self": "http://localhost:3000/articles/companies/nintendo-co-ltd"
    }
  },
  "included": [
    {
      "id": "2932",
      "type": "places",
      "attributes": {
        "name": "Kyoto",
        "formatted": "Kyoto, Kyoto Prefecture, Japan"
      },
      "links": {
        "self": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
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
    "keywords": "nintendo co., ltd., 1889, kyoto, kyoto prefecture, japan, company, profile, biography, trivia, dbljump, video games, pc games, gaming",
    "description": "Find Nintendo Co., Ltd.'s game credits, profile, images and facts at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:13.501Z",
    "updated_at": "2017-04-24T09:09:13.501Z"
  }
}
```

Retrieve a single company article. Companies are publicly available. No sign-in is required.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/companies/{slug}` (replace `{slug}` with record slug)

### Success HTTP response code

`200 OK`

### <a name="company_response_attrs"></a>Response attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
display_title | string | Y | The article title, usually the company name.
description | text | | A short biography up to 800 chars.
founded_date | date | | Between 1st Jan 1800 and the present.
founded_year | integer | | Between 1800 and the present year.
closed | boolean | | True if the company has closed.
closed_date | date | | Between 1st Jan 1800 and the present.
closed_year | integer | | Between 1800 and the present year.
slug | string | Y | A record ID based on the display_title.

### Relationships

Association | Record type | Relationship type
------------ | ---------- | -----------------
founded_place | places | belongs_to
hq_place | places | belongs_to
created_by | users | belongs_to


### Included

Record type | Relationship | Attributes included
----------- | ------------ | -------------------
users | created_by | username, role, given_names, family_name, avatar
places | founded_place | name, formatted
places | hq_place | name, formatted

### Meta

The `meta` section of the JSON response includes `keywords`, `description`, `created_at` and `updated_at` attributes.
