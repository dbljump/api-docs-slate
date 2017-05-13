## <a name="person_names_update"></a>Update a person name

> Request body | `PATCH /articles/person_names/41`

```JSON
{
  "data": {
    "type": "person_names",
    "id": "41",
    "attributes": {
      "given_names": "アップデート",
      "family_name": "カタカナ",
      "kind": "fullname",
      "writing_system": "Japanese",
      "year_adopted": "1995",
      "dropped": "true",
      "year_dropped": ""
    },
    "relationships": {
      "place": {
        "data": {
          "id": "102",
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
    "id": "41",
    "type": "person_names",
    "attributes": {
      "display_name": "カタカナ アップデート",
      "given_names": "アップデート",
      "family_name": "カタカナ",
      "kind": "fullname",
      "writing_system": "Japanese",
      "year_adopted": 1995,
      "dropped": true,
      "year_dropped": null
    },
    "relationships": {
      "person": {
        "data": {
          "id": "26",
          "type": "people"
        },
        "links": {
          "related": "http://localhost:3000/articles/people/satoru-iwata"
        }
      },
      "place": {
        "data": {
          "id": "102",
          "type": "places"
        },
        "links": {
          "related": "http://localhost:3000/places/japan"
        }
      }
    }
  },
  "included": [
    {
      "id": "26",
      "type": "people",
      "attributes": {
        "display_title": "Satoru Iwata"
      },
      "links": {
        "self": "http://localhost:3000/articles/people/satoru-iwata"
      }
    },
    {
      "id": "102",
      "type": "places",
      "attributes": {
        "name": "Japan"
      },
      "links": {
        "self": "http://localhost:3000/places/japan"
      }
    }
  ],
  "meta": {
    "keywords": "カタカナ アップデート, satoru iwata, japan, name, title, alias, dbljump, video games, pc games, gaming",
    "description": "カタカナ アップデート is an alternate name or title for Satoru Iwata. Learn more at Dbljump, the video game reference.",
    "created_at": "2017-04-24T09:09:17.343Z",
    "updated_at": "2017-05-13T13:21:47.547Z"
  }
}
```

Update an existing person name. The user must be an editor.

* User authentication: required
* Authorization level: admin

### HTTP request

`PATCH /articles/person_names/{id}` (replace `{id}` with record ID)

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
given_names | string | Y | 1-50 characters.
family_name | string |  | 1-50 characters.
kind | string | Y | The name classification. Must be 'name', 'fullname' or 'nickname'.
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

`200 OK`
