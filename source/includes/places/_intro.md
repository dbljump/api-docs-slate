# <a name="places_intro"></a>Places

Resources related to places.

### Kinds of place

There are four kinds of place, determined by the value of the `kind` attribute.

Kind | Description | Relationships
---- | ----------- | -------------
Region | A group of countries | Has many country `children`.
Country | A country, e.g. Japan | Belongs to many `regions`. Has many subdivision `children`.
Subdivision | An administrative area of a country, e.g. a county or state | Belongs to a `parent` country. Has many locality `children`.
Locality | A city or town | Belongs to a `parent` subdivision.

### Request attributes

See [Create a new place record](#places_create) and [Update a place record](#places_update).


### Response attributes

See [Get single place](#places_show).
