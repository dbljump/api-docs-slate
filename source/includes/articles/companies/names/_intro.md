# <a name="company_names_intro"></a>Articles: Company Names

Resources related to company names. The JSON:API type is `company_names`.

### Mutable attributes

#### `name` (string, required)

The name. 1-100 chars.

#### `kind` (string, required)

Name classification. Must be `name`, `styled` or `alias`.

#### `writing_system` (string, required)

Must be `Latin`, `Japanese`, `Cyrillic`, `Chinese` or `Arabic`.

#### `year_adopted` (integer)

Must be between `1800` and the present year.

#### `dropped` (boolean)

`true` if the name is no longer used. Auto-set to `true` if `year_dropped` is present.

#### `year_dropped` (integer)

Must be between `1800` and the present year, and greater than `year_adopted`.

### Relationships

Name | JSON:API type | Relationship type
------------ | ---------- | -----------------
`place` | `places` | `belongs_to`
`company` | `companies` | `belongs_to`
