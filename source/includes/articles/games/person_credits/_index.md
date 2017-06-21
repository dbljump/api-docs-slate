## Get all of a game's person-credits

> Response body | `HTTP 200`

```JSON
# GET /articles/games/the-wonderful-101/person_credits?page[size]=2


```

Retrieve all of a given game's person credits. Automatically paginated.

* User authentication: not required
* Authorization level: n/a

### HTTP request

`GET /articles/games/{game-slug}/person_credits` (replace `{game-slug}` with parent game record slug)

### URL query parameters

Parameter | Default | Description
--------- | ------- | -----------
fields[{record-type}] | All fields | Return only specified fields, e.g. `?fields[game_notes]=body`
filter[{field}] | All records | Filter search by field, e.g. `?filter[category]=Development`
page[number] | 1 | Select the page number, e.g. `?page[number]=3`
page[size] | 30 | Select the number of records per page, e.g. `?page[size]=20`

### Success HTTP response code

`200 OK`
