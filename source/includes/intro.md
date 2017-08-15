# Introduction

The Dbljump API is a system for cataloging and serving data about video games and the video game industry.

It is part of a wider group of software, Dbljump, which is made up of:

* The Dbljump [PostgreSQL](https://www.postgresql.org) database
* The back-end dbljump/rails-api, a [Ruby on Rails](http://rubyonrails.org) application that manages the database and provides the API described here. This is currently under development.
* The front-end client dbljump/client-ember, an [Ember.js](https://www.emberjs.com) application that provides a web user interface. This is currently under development.
* [Dbljump.com](http://www.dbljump.com), the web domain where it all comes together

This API is therefore designed to be used exclusively by the Dbljump front-end client.

This documentation, which describes the features of the API and how to use them, is intended for use by the Dbljump development team. It was built with [Slate](https://github.com/lord/slate) and is hosted with [GitHub Pages](https://pages.github.com).

**For more information, or if you want to contribute or join us, please visit [www.dbljump.com](http://www.dbljump.com).**

## How to use

Basic rules for making API requests.

### Domain

URLs in this documentation exclude the domain where the production API is hosted. Prepend the current domain name to URLs when making requests, e.g. `http://api.dbljump.com/articles/games`.

### JSON API specification

This API accepts and returns JSON data, following the JSON API specification as closely as possible.

[Read more about the specification](http://jsonapi.org).

### HTTP headers: request content-type and version

In accordance with the JSON API spec, all requests must include two HTTP headers, which declare the content-type and API version number:

* `Accept:application/vnd.api+json; version={vnum}`
* `Content-Type:application/vnd.api+json; version={vnum}`

Replace `{vnum}` with the API version number you want to use. The current version number is `1`, and this is not expected to change anytime soon!

### HTTP headers: response content-type

Successful responses include the following HTTP header:

* `Content-Type:application/vnd.api+json; charset=utf-8`

## Authorizing requests and logging in users

Many Dbljump API requests require authorization. This API uses JWTs for authentication and authorization, instead of HTTP sessions. When authorization is needed, it must be provided via a [JSON web token (JWT)](https://jwt.io) included in the `Authorization` HTTP header.

The presence and [payload content](#the-jwt-payload) of a JWT determines:

* whether or not a user is 'logged in'
* the authorization level of the user identified by the JWT
* whether the request is authorized (based on the validity of the JWT and the user's authorization level)

### HTTP headers: request authorizations

A valid `Authorization` header and JWT must always be _included_ when the client user is logged in and always _excluded_ when the client user is not logged in.

The header must be provided as follows:

* `Authorization:Bearer {user-jwt}`

Replace `{user-jwt}` with a JWT returned by a successful [user authentication request](#users-authentications).

### The JWT payload

As well providing request authorization, JWTs contain a JSON payload the client can decode and use to identify the logged-in user.

JWT payload attribute | Description
--------------------- | -----------
`user_id` | Can be used to [get the logged-in user's record](#get-single-user).
`user_role` | Determines the user's authorization level. Can be `member`, `editor` or `admin`.
`expiry` | The JWT expiry date and time.

### User role and authorization level

API request authorization also depends on the `role` of the user that the passed JWT belongs to.

Users can have one of three roles:

Role                | Description
------------------- | -----------
`member`            | Ordinary user. Can sign in and view pages but has very limited abilities.
`editor`            | Can create, edit (and in some cases delete) articles and images.
`admin`             | Can do everthing, including managing users, places, platform, genres and so on.

This documentation describes the authorization level required to use each each API feature.

## Using URL queries

> URL query examples

```
# Include all primary_image items related to articles in the response:
/articles/games?include=primary_image

# Specify sparse fieldsets for users and images (users are included by
# default):
/users/2/images?fields[users]=username,avatar&fields[images]=title,thumb

# Use filter to only return items where kind == 'photo':
/media/images?filter[kind]=photo

# Specify 10 items per page and return page 5:
/users?page[size]=10&page[number]=5

# Sort by two fields: kind (ascending) and created_by_id (descending
# as prepended by a dash):
/media/images?sort=kind,-created_by_id
```

This API supports five kinds of URL queries for fetching data, [as specified by JSON API](http://jsonapi.org/format/#fetching):

* included resources
* sparse fieldsets
* sorting
* pagination
* filtering by field values

Query type     | Description
-------------- | -----------
`include`      | Include resources related to the main dataset.
`fields`       | Specify sparse fieldsets. You must provide the type(s) and field name(s).
`filter`       | Filter data by a given field and value.
`page[size]`   | Specify how many items should be on each page. Defaults to `30`.
`page[number]` | Specify the page number. Defaults to `1`.
`sort`         | Sort the data by specified fields. Prepend the field name with a `-` to sort descending.
