## <a name="platforms_create"></a>Create a new platform record

> Request body

```JSON
{
  "data": {
    "type": "platforms",
    "attributes": {
      "name": "New Platform",
      "short_name": "NPlat",
      "sphere": "home",
      "kind": "add-on",
      "holder_id": "1",
      "parent_id": "13"
    }
  }
}
```

> HTTP 201 response body

```JSON
{
  "data": {
    "id": "39",
    "type": "platforms",
    "attributes": {
      "slug": "nintendo-new-platform",
      "name": "New Platform",
      "short_name": "NPlat",
      "sphere": "home",
      "kind": "add-on"
    },
    "relationships": {
      "holder": {
        "meta": {}
      },
      "parent": {
        "data": {
          "id": "13",
          "type": "platforms"
        },
        "links": {
          "related": "http://api.dbljump.com/platforms/nintendo-switch"
        }
      },
      "created_by": {
        "data": {
          "id": "2",
          "type": "users"
        },
        "links": {
          "related": "http://api.dbljump.com/users/2"
        }
      }
    },
    "links": {
      "self": "http://api.dbljump.com/platforms/nintendo-new-platform"
    }
  },
  "included": [
    {
      "id": "2",
      "type": "users",
      "attributes": {
        "username": "neil",
        "role": "admin",
        "given_names": "Neil",
        "family_name": "Wheatley",
        "avatar": {
          "url": "https://dbljumpheroku.s3.amazonaws.com/uploads/user_avatar/2/1703301240.jpg"
        }
      },
      "links": {
        "self": "http://api.dbljump.com/users/2"
      }
    }
  ],
  "meta": {
    "keywords": "new platform, nplat, nintendo, home, add-on, platform, dbljump, video games, pc games, gaming",
    "description": "Find out about games for New Platform by Nintendo Co., Ltd. at Dbljump, the video game reference.",
    "created_at": "2017-03-30T13:32:37.200Z",
    "updated_at": "2017-03-30T13:32:37.200Z"
  }
}
```

Create a new platform record. Admin-level authorization required.

* User authentication: required
* Authorization level: admin

### HTTP request

`POST /platforms`

### Request attributes

Attribute | Type | Req'd? | Description
--------- | ---- | ------ | -----------
name | string | Y | Max 50 chars. The full North American name, or nearest alternative, e.g. 'Genesis'
short_name | string | | Max 10 chars. The common abbreviated name, e.g. 'SNES'.
sphere | string | Y | The usual platform environment. See [Sphere](#platforms_sphere).
kind | string | Y | Platform type. See [Kind](#platforms_kind).
holder_id | integer | Y | Must be a valid company ID. The platform holder, e.g. 'Sony' for PlayStation.
parent_id | integer | Y | Must be a valid platform ID. Used for add-ons, e.g. 'Sega CD' belongs to Sega Genesis.

### <a name="platforms_sphere"></a>Sphere

The `sphere` attribute must take one of the following values.

Value | Description
----- | -----------
home | Usually used at home, e.g. a home console or computer.
portable | Portable or handheld, e.g. PS Vita or Nintendo Game Boy.
mobile | A phone, tablet or mobile operating system, e.g. Android.
arcade | Associated with public game arcades, e.g. Sega NAOMI.
non-gaming | For platforms not usually associated with gaming.

### <a name="platforms_kind"></a>Kind

The `kind` attribute must take one of the following values.

Value | Description
----- | -----------
system | Hardware such as a console, computer or device.
OS | A software operating system that might run on various devices.
add-on | A device that requires its parent platform to run.

### Success HTTP response code

`201 Created`
