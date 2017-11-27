# Articles: Game Aliases

Resources related to game aliases. An alias is another title the game is known by. The JSON:API type is `game_aliases`.

### Mutable attributes

#### `display_text` (string, required)

The alias. 1-250 chars.

#### `kind` (string, required)

Name classification. Must be `title`, `working` or `translated`.

#### `writing_system` (string, required)

Must be `Latin`, `Japanese`, `Cyrillic`, `Chinese` or `Arabic`.

### Relationships

Name         | JSON:API type   | Relationship type | Required?
------------ | --------------- | ----------------- | ---------
`game`       | `games`         | `belongs_to`      | Y
`version`    | `game_versions` | `belongs_to`      |  
`place`      | `places`        | `belongs_to`      |
