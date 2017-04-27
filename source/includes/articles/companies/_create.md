## <a name="comanies_create"></a>Create a new company

> Request body | `POST /articles/companies`

```JSON
{
  "data": {
    "type": "companies",
    "attributes": {
      "display_title": "New Company",
      "description": "New Company is a new company, and this describes it.",
      "founded_date": "1965-09-12",
      "founded_year": "",
      "closed": "",
      "closed_date": "2012-05-18",
      "closed_year": ""
    },
    "relationships": {
      "founded_place": {
        "data": {
          "id": "2883",
          "type": "places"
        }
      },
      "hq_place": {
        "data": {
          "id": "2932",
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
    "id": "49",
    "type": "companies",
    "attributes": {
      "display_title": "New Company",
      "description": "New Company is a new company, and this describes it.",
      "founded_date": "1965-09-12",
      "founded_year": 1965,
      "closed": true,
      "closed_date": "2012-05-18",
      "closed_year": 2012,
      "slug": "new-company"
    },
    "relationships": {
      "founded_place": {
        "data": {
          "id": "2883",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/los-angeles-california-united-states"
        }
      },
      "hq_place": {
        "data": {
          "id": "2932",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/kyoto-kyoto-prefecture-japan"
        }
      },
      "created_by": {
        "data": {
          "id": "2",
          "type": "users"
        },
        "links": {
          "related": "http://localhost:3000/users/2"
        }
      }
    },
    "links": {
      "self": "http://localhost:3000/articles/companies/new-company"
    }
  },
  "included": [
    {
      "id": "2883",
      "type": "places",
      "attributes": {
        "name": "Los Angeles",
        "formatted": "Los Angeles, California, United States"
      },
      "links": {
        "self": "http://localhost:3000/places/los-angeles-california-united-states"
      }
    },
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
      "id": "2",
      "type": "users",
      "attributes": {
        "username": "neil",
        "role": "admin",
        "given_names": "Neil",
        "family_name": "Wheatley",
        "avatar": "http://localhost:3000/uploads/user_avatar/2/1704241009.jpg"
      },
      "links": {
        "self": "http://localhost:3000/users/2"
      }
    }
  ],
  "meta": {
    "keywords": "new company, 1965, los angeles, california, united states, kyoto, kyoto prefecture, japan, company, profile, biography, trivia, dbljump, video games, pc games, gaming",
    "description": "Find New Company's game credits, profile, images and facts at Dbljump, the video game reference.",
    "created_at": "2017-04-27T09:04:34.137Z",
    "updated_at": "2017-04-27T09:04:34.137Z"
  }
}
```

Create a new company article. User must be an editor or admin.

* User authentication: required
* Authorization level: editor or admin

### HTTP request

`POST /articles/companies`

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
founded_place | belongs_to | | places | Can be a country, subdivision, or locality.
closed_place | belongs_to | | places | Can be a country, subdivision, or locality.

### Success HTTP response code

`201 Created`
