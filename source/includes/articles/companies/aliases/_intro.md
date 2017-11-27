# Articles: Company Aliases

Resources related to company aliases. An alias is another name the company is known by. The JSON:API type is `company_aliases`.

### Mutable attributes

#### `display_text` (string, required)

The alias. 1-100 chars.

#### `kind` (string, required)

Name classification. Must be `name`, `styled` or `AKA`.

#### `writing_system` (string, required)

Must be `Latin`, `Japanese`, `Cyrillic`, `Chinese` or `Arabic`.

#### `year_adopted` (integer)

Must be between `1800` and the present year.

#### `dropped` (boolean)

`true` if the alias is no longer used. Auto-set to `true` if `year_dropped` is present.

#### `year_dropped` (integer)

Must be between `1800` and the present year, and greater than `year_adopted`.

### Relationships

Name | JSON:API type | Relationship type
------------ | ---------- | -----------------
`place` | `places` | `belongs_to`
`company` | `companies` | `belongs_to`
